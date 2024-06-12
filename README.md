# Firefox: hacks, tweaks, and productivity enhancements

Below are a few of our favorite Firefox hacks, tweaks, and productivity enhancements that can be made via [Configuration Editor](https://support.mozilla.org/en-US/kb/about-config-editor-firefox) (about:config page).

## Security

Disable WebRTC

```json
media.peerconnection.enabled => false
```

Firefox already has an Enhanced Tracking Protection feature that blocks a list of known "fingerprinters" when your privacy settings are set to Standard (the default) or Strict, whereas [Fingerprinting Protection](https://support.mozilla.org/en-US/kb/firefox-protection-against-fingerprinting) is a different, experimental feature under heavy development in Firefox

```json
privacy.resistFingerprinting => true
privacy.trackingprotection.fingerprinting.enabled => true
```

Enable IDN Punycode (display the "raw", punycode version of internationalized domain names)

```json
network.IDN_show_punycode => true
```

## Privacy

Enable Container Tabs and its UI setting. [Firefox containers](https://support.mozilla.org/en-US/kb/how-use-firefox-containers) let you separate your browsing activities into color-coded tabs for banking, work and personal browsing. This allows you to always open new tabs in containers of your choosing for a more private browsing experience. Each container is isolated from the others, so you can access sites logged into different accounts.

```json
privacy.userContext.enabled => true
privacy.userContext.ui.enabled => true
privacy.userContext.newTabContainerOnLeftClick.enabled => true
```

Disable Geolocation Tracking

```json
geo.enabled => false
```

Disables the Widevine Content Decryption Module provided by Google

```json
media.gmp-widevinecdm.enabled => false
```

Disable Pocket integration

```json
extensions.pocket.enabled => false
```

## Telemetry

This is the data submission master kill switch: if disabled, no policy is shown or upload takes place (https://firefox-source-docs.mozilla.org/toolkit/components/telemetry/internals/preferences.html)

```json
datareporting.policy.dataSubmissionEnabled => false
```

Disable recommendations in about:addons' Extensions and Themes panes

```json
extensions.htmlaboutaddons.recommendations.enabled => false
```

## DOM

Web pages won't be allowed to manipulate or block the context menu

```json
dom.event.contextmenu.enabled => false
```

Prevent scripts from moving and resizing open windows

```json
dom.disable_window_move_resize => false
```

## UI

Open bookmarks in a new tab (rather than existing window)

```json
browser.tabs.loadBookmarksInTabs => true
```

Prevent Firefox from exiting when you close the last tab

```json
browser.tabs.closeWindowWithLastTab => false
```

This preference controls whether lines in View Source that are too long to fit the window will wrap to the next line or cause a horizontal scroll bar

```json
view_source.wrap_long_lines => true
```

Compact mode workaround in Firefox. Starting with Firefox 89, the Compact Density option is hidden by default in Menu > Customize toolbar... The following settings will help you get this option back.

```json
browser.compactmode.show => true
```

Next step: More tools -> Customize toolbar... -> Density -> Compact (not supported)

## Color correction

Color management allows images and colors to be displayed consistently across a variety of devices. Mozilla recognizes embedded ICC profiles in image files and uses a local color profile to perform the color adjustments. This preference determines if Mozilla should make these adjustments.

```json
gfx.color_management.mode

0 -> Disable color management
1 -> Enable color management for rendered graphics
2 -> Enable color management for tagged graphics only (Default)
```
