# Corne ZMK Config

This folder is a fresh `zmk-config` for a `Corne` on `nice!nano` with `ZMK Studio` support enabled on the left half.

## Files

- `build.yaml`: GitHub Actions build matrix
- `config/corne.keymap`: keymap rebuilt from the Studio screenshots
- `config/corne.conf`: runtime options
- `config/west.yml`: ZMK manifest
- `.github/workflows/build.yml`: build workflow

## Notes

- `Layer 4` is now a service layer with Bluetooth profile switching, output switching, `Caps Word`, `Studio Unlock`, `Soft Off`, and the existing `Ctrl+Space`.
- `CONFIG_BT_CTLR_PHY_2M=n` is enabled because it can improve Bluetooth compatibility on some hosts.
- `Layer 3` was mapped as a keypad-style block because the screenshot layout matched a numpad arrangement.
- The config is intended to stay editable in `ZMK Studio`. Once flashed, Studio changes will live on the keyboard until you reset them.

## Build

1. Create a new GitHub repo and copy this folder into it, or initialize git here.
2. Push the repo to GitHub.
3. Open the `Actions` tab and wait for the workflow to finish.
4. Download the firmware artifact zip.
5. Flash the `corne_left` UF2 to the left half and the `corne_right` UF2 to the right half.

## Flash

1. Plug in one half over USB.
2. Double-tap reset on the `nice!nano`.
3. Wait for the `NICENANO` drive to appear.
4. Copy the matching `.uf2` file onto it.
5. Repeat for the other half.

## Studio

- Use the left half for `ZMK Studio`.
- If needed, switch output with the `Layer 4` keys: `OUT_USB`, `OUT_BLE`, or `OUT_TOG`.
- If Studio is locked, use the `studio_unlock` key on `Layer 4`.
