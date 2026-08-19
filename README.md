# Genesis DH head-unit byte patches

This repository contains independent binary patch recipes for the Genesis DH
head unit. Each recipe uses the `dh-headunit-application-patch/v2` schema and
matches an exact stock file size and SHA-256 identity before changing bytes.
Unknown software builds are rejected instead of being patched.

The catalog was developed against the `2017_Genesis_G80_EU` update,
`DHPE.EUR.SOP.03.013.20230825`. See each recipe's `_comment` field for its
individual vehicle-test status.

## Patch catalog

| Patch | Description |
| --- | --- |
| `android-auto-density-214` | Sets Android Auto's 1280×720 display density to 214 DPI to correct scaling. |
| `android-auto-media-title-bridge` | Shows the current Android Auto media title on the instrument cluster. |
| `android-auto-mute-pause` | Pauses Android Auto playback when muted and resumes it when unmuted. |
| `android-auto-render-latency` | Drops stale decoded Android Auto frames when rendering falls behind. |
| `android-auto-touch-bound` | Rejects Android Auto touch events containing more than five contacts. |
| `bt-metadata-marquee` | Scrolls long Bluetooth device, title, artist, and album text. |
| `bt-repeat-shuffle` | Shows Bluetooth repeat and shuffle controls when supported by the connected player. |
| `carplay-iap2-short-write` | Preserves CarPlay USB transfers when the device accepts only part of a packet. |
| `carplay-media-title-bridge` | Shows the current CarPlay media title on the instrument cluster. |
| `carplay-multitouch` | Enables two-finger CarPlay gestures such as pinch-to-zoom. |
| `carplay-mute-pause` | Pauses CarPlay playback when muted and resumes it when unmuted. |
| `carplay-render-latency` | Drops stale decoded CarPlay frames when rendering falls behind. |
| `carplay-role-switch-race` | Prevents completed CarPlay USB role switches from being reported as timeouts and limits stalled attempts. |
| `carplay-startup-ready-races` | Prevents CarPlay startup hangs caused by early readiness or failed USB-monitor startup. |
| `carplay-transport-ready-per-instance` | Tracks readiness separately for each CarPlay transport and limits waits for stalled transports. |
| `engineering-list3-labels` | Corrects Engineering Log List 3 labels for AppSettingsBT and AppIBox. |
| `engineering-qcan-critical-level` | Makes QCANController CRITICAL persist and report as CRITICAL instead of ASSERT. |
| `hvac-rear-on-off` | Shows the rear climate state as REAR ON or REAR OFF on the Climate screen. |
| `projection-usb-control-timeouts` | Adds bounded Android Auto and CarPlay USB control-request waits and rejects incomplete CarPlay capability replies. |

## Layout

All recipes are stored directly in `byte_patches/`. Copy that directory into
the corresponding catalog location used by the SD patcher or image builder.
