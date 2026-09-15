# Homebrew tap for quietmouse

[quietmouse](https://github.com/benjweaver/quietmouse) gives you offline,
telemetry-free settings, buttons and gestures for Logitech mice.

```sh
brew install benjweaver/quietmouse/quietmouse
quietmouse config --init
quietmouse autostart on
```

On macOS, allow `quietmoused` under System Settings → Privacy & Security, in Input
Monitoring and in Accessibility (called Device Control and Data Access on newer macOS).
macOS ties those permissions to the exact binary, so after `brew upgrade quietmouse`,
allow it again and then run `quietmouse stop` and `quietmouse start`.

On Linux, the formula's caveats show the one-time command to install the udev rule. The
distribution packages on the quietmouse Releases page install it for you.

The formula installs the prebuilt release binaries: universal on macOS, x86_64 on Linux.
`scripts/update-formula.sh` regenerates `Formula/quietmouse.rb` from each release's
published checksums. A workflow runs it every six hours and then tests the formula.
