# Changelog

Shoelace follows [Semantic Versioning](https://semver.org/). Breaking changes in components with the <sl-badge variant="primary" pill>Stable</sl-badge> badge will not be accepted until the next major version. As such, all contributions must consider the project's roadmap and take this into consideration. Features that are deemed no longer necessary will be deprecated but not removed.

Components with the <sl-badge variant="warning" pill>Experimental</sl-badge> badge should not be used in production. They are made available as release candidates for development and testing purposes. As such, changes to experimental components will not be subject to semantic versioning.

New versions of Shoelace are released as-needed and generally occur when a critical mass of changes have accumulated. At any time, you can see what's coming in the next release by visiting [next.shoelace.style](https://next.shoelace.style).

_During the beta period, these restrictions may be relaxed in the event of a mission-critical bug._ 🐛

## Next

- Added `button--checked` to `<sl-radio-button>` and `control--checked` to `<sl-radio>` to style just the checked state [#933](https://github.com/shoelace-style/shoelace/pull/933)
- Fixed a bug in `<sl-card>` that prevented the border radius to apply correctly to the header [#934](https://github.com/shoelace-style/shoelace/pull/934)
- Improved `<sl-badge>` so it renders relative to the current font size and improved padding
- Added tests for `<sl-menu-item>` and `<sl-menu-label>` [#935](https://github.com/shoelace-style/shoelace/pull/935)

## 2.0.0-beta.83

This release removes the `<sl-responsive-media>` component. When this component was introduced, support for [`aspect-radio`](https://developer.mozilla.org/en-US/docs/Web/CSS/aspect-ratio)) wasn't great. These days, [the property is supported](https://caniuse.com/mdn-css_properties_aspect-ratio) by all of Shoelace's target browsers, making a dedicated component redundant.

- 🚨 BREAKING: Removed `<sl-responsive-media>` (use the well-supported `aspect-ratio` CSS property instead)
- 🚨 BREAKING: Changed the `toggle-password` attribute of `<sl-input>` to `password-toggle` for consistency
- Added an expand/collapse animation to `<sl-tree-item>`
- Added `sl-lazy-change` event to `<sl-tree-item>`
- Added `expand-button` part to `<sl-tree-item>` [#893](https://github.com/shoelace-style/shoelace/pull/893)
- Added `password-visible` attribute to `<sl-input>` [#913](https://github.com/shoelace-style/shoelace/issues/913)
- Fixed a bug in `<sl-popup>` that didn't account for the arrow's diagonal size
- Fixed a bug in `<sl-popup>` that caused arrow placement to be incorrect with RTL
- Fixed a bug in `<sl-progress-ring>` that caused the indeterminate animation to stop working in Safari [#891](https://github.com/shoelace-style/shoelace/issues/891)
- Fixed a bug in `<sl-range>` that caused it to overflow a container at 100% width [#905](https://github.com/shoelace-style/shoelace/issues/905)
- Fixed a bug in `<sl-tree-item>` that prevented custom expand/collapse icons from rendering
- Fixed a bug in `<sl-tree-item>` where the `expand-icon` and `collapse-icon` slots were reversed
- Fixed a bug in `<sl-tree-item>` that prevented the keyboard from working after lazy loading [#882](https://github.com/shoelace-style/shoelace/issues/882)
- Fixed a bug in `<sl-textarea>` that prevented the textarea from resizing automatically when setting the value programmatically [#912](https://github.com/shoelace-style/shoelace/discussions/912)
- Fixed a handful of paths to prevent TypeScript from getting upset [#886](https://github.com/shoelace-style/shoelace/issues/886)
- Fixed a bug in `<sl-radio-group>` where the `button-group__base` part was documented but not exposed [#909](https://github.com/shoelace-style/shoelace/discussions/909)
- Fixed a bug in `<sl-range>` that caused the active track color to render on the wrong side in RTL [#916](https://github.com/shoelace-style/shoelace/issues/916)
- Refactored the internal event emitter to be part of `ShoelaceElement` to reduce imports and improve DX
- Downgraded Floating UI from 1.0.1 to 1.0.0 due to new logic that makes positioning much slower for certain components [#915](https://github.com/shoelace-style/shoelace/issues/915)
- Upgraded the status of `<sl-animated-image>`, `<sl-popup>`, and `<sl-split-panel>` from experimental to stable

## 2.0.0-beta.82

- Added the `sync` and `arrow-placement` attributes to `<sl-popup>`
- Changed the `auto-size` attribute of the experimental `<sl-popup>` component so it accepts `horizontal`, `vertical`, and `both` instead of a boolean value
- Changed the `flip-fallback-placement` attribute of the experimental `<sl-popup>` component to `flip-fallback-placements`
- Changed the `flip-fallback-strategy` in the experimental `<sl-popup>` component to accept `best-fit` and `initial` instead of `bestFit` and `initialPlacement`
- Fixed a bug in `<sl-dropdown>` that caused the panel to resize horizontally when the trigger is clipped by the viewport [#860](https://github.com/shoelace-style/shoelace/issues/860)
- Fixed a bug in `<sl-tree>` where dynamically changing slotted items wouldn't update the tree properly
- Fixed a bug in `<sl-split-panel>` that caused the panel to stack when clicking on the divider in mobile versions of Chrome [#862](https://github.com/shoelace-style/shoelace/issues/862)
- Fixed a bug in `<sl-popup>` that prevented flip fallbacks from working as intended
- Fixed a bug that caused concurrent animations to work incorrectly when the durations were different [#867](https://github.com/shoelace-style/shoelace/issues/867)
- Fixed a bug in `<sl-color-picker>` that caused the trigger and color preview to ignore opacity on first render [#869](https://github.com/shoelace-style/shoelace/issues/869)
- Fixed a bug in `<sl-tree>` that prevented the keyboard from working when the component was nested in a shadow root [#871](https://github.com/shoelace-style/shoelace/issues/871)
- Fixed a bug in `<sl-tab-group>` that prevented the keyboard from working when the component was nested in a shadow root [#872](https://github.com/shoelace-style/shoelace/issues/872)
- Fixed a bug in `<sl-tab>` that allowed disabled tabs to erroneously receive focus
- Improved single selection in `<sl-tree>` so nodes expand and collapse and rece
  ive selection when clicking on the label
- Renamed `expanded-icon` and `collapsed-icon` slots to `expand-icon` and `collapse-icon` in the experimental `<sl-tree>` and `<sl-tree-item>` components
- Improved RTL support for `<sl-image-comparer>`
- Refactored components to extend from `ShoelaceElement` to make `dir` and `lang` reactive properties in all components

## 2.0.0-beta.81

- 🚨 BREAKING: removed the `base` part from `<sl-menu>` and removed an unnecessary `<div>` that made styling more difficult
- Added the `anchor` property to `<sl-popup>` to support external anchors
- Added read-only custom properties `--auto-size-available-width` and `--auto-size-available-height` to `<sl-popup>` to improve support for overflowing popup content
- Added `label` to `<sl-rating>` to improve accessibility for screen readers
- Added the `base__popup` and `base__arrow` parts to `<sl-tooltip>` [#858](https://github.com/shoelace-style/shoelace/issues/858)
- Fixed a bug where auto-size wasn't being applied to `<sl-dropdown>` and `<sl-select>`
- Fixed a bug in `<sl-popup>` that caused auto-size to kick in before flip
- Fixed a bug in `<sl-popup>` that prevented the `arrow-padding` attribute from working as expected
- Fixed a bug in `<sl-tooltip>` that prevented the popup from appearing with the correct z-index [#854](https://github.com/shoelace-style/shoelace/issues/854)
- Improved accessibility of `<sl-rating>` so keyboard nav works better and screen readers announce it properly
- Improved accessibility of `<sl-spinner>` so screen readers no longer skip over it
- Removed a user agent sniffing notice that appeared in Chrome [#855](https://github.com/shoelace-style/shoelace/issues/855)
- Removed the default hover effect in `<sl-tree-items>` to make selections more obvious
- Updated Floating UI to 1.0.1
- Updated esbuild to 0.15.1
- Updated all other dependencies to latest versions

## 2.0.0-beta.80

This release breaks radio buttons, which is something that needed to happen to solve a longstanding accessibility issue where screen readers announced an incorrect number of radios, e.g. "1 of 1" instead of "1 of 3." Many attempts to solve this without breaking the existing API were made, but none worked across the board. The new implementation upgrades `<sl-radio-group>` to serve as the "form control" while `<sl-radio>` and `<sl-radio-button>` serve as options within the form control.

To upgrade to this version, you will need to rework your radio controls by moving `name` up to the radio group. And instead of setting `checked` to select a specific radio, you can set `value` on the radio group and the checked item will update automatically.

- 🚨 BREAKING: improved accessibility of `<sl-radio-group>`, `<sl-radio>`, and `<sl-radio-button>` so they announce properly in screen readers
  - Added the `name` attribute to `<sl-radio-group>` and removed it from `<sl-radio>` and `<sl-radio-button>`
  - Added the `value` attribute to `<sl-radio-group>` (use this to control which radio is checked)
  - Added the `sl-change` event to `sl-radio-group`
  - Added `setCustomValidity()` and `reportValidity()` to `<sl-radio-group>`
  - Removed the `checked` attribute from `<sl-radio>` and `<sl-radio-button>` (use the radio group's `value` attribute instead)
  - Removed the `sl-change` event from `<sl-radio>` and `<sl-radio-button>` (listen for it on the radio group instead)
  - Removed the `invalid` attribute from `<sl-radio>` and `<sl-radio-button>`
  - Removed `setCustomValidity()` and `reportValidity()` from `<sl-radio>` and `<sl-radio-button>` (now available on the radio group)
- Added the experimental `<sl-popup>` component
- Fixed a bug in `<sl-menu-item>` where labels weren't always aligned correctly
- Fixed a bug in `<sl-range>` that caused the tooltip to be positioned incorrectly when switching between LTR/RTL
- Refactored `<sl-dropdown>` to use `<sl-popup>`
- Refactored `<sl-tooltip>` to use `<sl-popup>` and added the `body` part
- Revert disabled focus behavior in `<sl-tab-group>`, `<sl-menu>`, and `<sl-tree>` to be consistent with native form controls and menus [#845](https://github.com/shoelace-style/shoelace/issues/845)

## 2.0.0-beta.79

- Added experimental `<sl-tree>` and `<sl-tree-item>` components [#823](https://github.com/shoelace-style/shoelace/pull/823)
- Added `--indicator-width` custom property to `<sl-progress-ring>` [#837](https://github.com/shoelace-style/shoelace/issues/837)
- Added Swedish translation [#838](https://github.com/shoelace-style/shoelace/pull/838)
- Added support for `step="any"` for `<sl-input type="number">` [#839](https://github.com/shoelace-style/shoelace/issues/839)
- Changed the type of component styles from `CSSResult` to `CSSResultGroup` [#828](https://github.com/shoelace-style/shoelace/issues/828)
- Fixed a bug in `<sl-color-picker>` where using <kbd>Left</kbd> and <kbd>Right</kbd> would select the wrong color
- Fixed a bug in `<sl-dropdown>` that caused the position to be incorrect on the first show when using `hoist` [#843](https://github.com/shoelace-style/shoelace/issues/843)
- Fixed a bug in `<sl-tab-group>` where the divider was on the wrong side when using `placement="end"`
- Fixed a bug in `<sl-tab-group>` that caused nested tab groups to scroll when using `placement="start|end"` [#815](https://github.com/shoelace-style/shoelace/issues/815)
- Fixed a bug in `<sl-tooltip>` that caused the target to be lost after a slot change [#831](https://github.com/shoelace-style/shoelace/pull/831)
- Fixed a bug in `<sl-tooltip>` that caused the position to be incorrect on the first show when using `hoist`
- Improved accessibility of `<sl-tab-group>`, `<sl-tab>`, and `<sl-tab-panel>` to announce better in screen readers and by allowing focus on disabled items
- Improved accessibility of `<sl-menu>` and `<sl-menu-item>` by allowing focus on disabled items
- Updated Lit to 2.2.8
- Update esbuild to 0.14.50
- Updated Bootstrap Icons to 1.9.1
- Updated Floating UI to 1.0.0
- Updated all other dependencies to latest versions

## 2.0.0-beta.78

- 🚨 BREAKING: Moved the `checked-icon` and `indeterminate-icon` parts from a wrapper `<span>` to the `<svg>` in `<sl-checkbox>` [#786](https://github.com/shoelace-style/shoelace/issues/786)
- 🚨 BREAKING: Moved the `checked-icon` part from a wrapper `<span>` to the `<svg>` in `<sl-radio>` [#786](https://github.com/shoelace-style/shoelace/issues/786)
- Added the `--track-active-offset` custom property to `<sl-range>` [#806](https://github.com/shoelace-style/shoelace/issues/806)
- Fixed a bug that caused `<sl-select>` to sometimes have two vertical scrollbars [#814](https://github.com/shoelace-style/shoelace/issues/814)
- Fixed a bug that caused a gray line to appear between radio buttons [#821](https://github.com/shoelace-style/shoelace/discussions/821)
- Fixed a bug that caused `<sl-animated-image>` to not render anything when using the `play` attribute initially [#824](https://github.com/shoelace-style/shoelace/issues/824)
- Removed `:focus-visible` shim now that the last two major versions of Safari support it
- Updated Bootstrap Icons to 1.9.0
- Updated esbuild to 0.14.49
- Updated Floating UI to 0.5.4
- Updated Lit to 2.2.7
- Updated all other dependencies to latest versions

## 2.0.0-beta.77

- Added styles to required form controls so they show an asterisk next to the label by default
- Added the `--sl-input-required-content` design token
- Added the `required` attribute to `<sl-radio-group>` and fixed constraint validation logic to support custom validation
- Added the `checked-icon` part to `<sl-menu-item>`
- Added the `no-spin-buttons` attribute to `<sl-input type="number">` [#798](https://github.com/shoelace-style/shoelace/issues/798)
- Added support for resetting forms using `<sl-button type="reset">` [#799](https://github.com/shoelace-style/shoelace/pull/799)
- Fixed a bug where a duplicate clear button showed in Firefox [#791](https://github.com/shoelace-style/shoelace/issues/791)
- Fixed a bug where setting `valueAsDate` or `valueAsNumber` too early on `<sl-input>` would throw an error [#796](https://github.com/shoelace-style/shoelace/issues/796)
- Fixed a bug in `<sl-color-picker>` where empty values weren't properly supported [#797](https://github.com/shoelace-style/shoelace/issues/797)
- Fixed a bug in `<sl-color-picker>` where values were logged to the console when using the keyboard
- Fixed a bug in `<sl-input>` where password controls would try to autocorrect/autocomplete/autocapitalize when the password is visible
- Fixed label alignment in `<sl-checkbox>` and `<sl-radio>` so they align to the top of the control instead of the center when wrapping
- Fixed labels in `<sl-checkbox>` and `<sl-radio>` so they use the `--sl-input-label-color` design token
- Improved performance of the tabbable utility which can prevent the browser from temporarily locking up in focus traps [#800](https://github.com/shoelace-style/shoelace/pull/800)
- Updated the `fieldset` attribute so it reflects in `<sl-radio-group>`

## 2.0.0-beta.76

- Added support for RTL animations in the Animation Registry
- Fixed a bug where the bottom border of `<sl-select>` could be cut off when the dropdown scrolls
- Fixed a bug in `<sl-select>` that could result in the browser locking up due to an infinite positioning loop [#777](https://github.com/shoelace-style/shoelace/issues/777)
- Improved RTL animations for `<sl-drawer>` [#784](https://github.com/shoelace-style/shoelace/issues/784)
- Improved RTL styles for `<sl-button-group>` [#783](https://github.com/shoelace-style/shoelace/issues/783)
- Improved RTL styles for the toast stack [#785](https://github.com/shoelace-style/shoelace/issues/785)
- Improved typings for translations and localized terms
- Upgraded @shoelace-style/localize to 3.0

## 2.0.0-beta.75

- Added Persian translation [#774](https://github.com/shoelace-style/shoelace/pull/774)
- Added `color-scheme` to light and dark themes to improve rendering of browser-provided UI [#776](https://github.com/shoelace-style/shoelace/issues/776)
- Added `--track-width` custom property to `<sl-tab-group>`
- Fixed focus rings for `<sl-input>`, `<sl-select>`, and `<sl-textarea>` in Safari since they don't use `:focus-visible` [#767](https://github.com/shoelace-style/shoelace/issues/767)
- Fixed a bug where calling `HTMLFormElement.reportValidity()` would skip Shoelace form controls [#772](https://github.com/shoelace-style/shoelace/issues/772)
- Fixed a bug that prevented `<sl-tooltip>` from closing when disabled [#775](https://github.com/shoelace-style/shoelace/issues/775)
- Fixed a bug that allowed `<sl-icon-button>` to emit a `click` event when disabled [#781](https://github.com/shoelace-style/shoelace/issues/781)
- Improved the default icon for `<sl-image-comparer>` so it's more intuitive and removed `grip-vertical` from system icon library
- Improved RTL styles for many components [#768](https://github.com/shoelace-style/shoelace/pull/768)
- Improved base path logic to execute only when `getBasePath()` is first called to better support SSR [#778](https://github.com/shoelace-style/shoelace/issues/778)
- Improved `DOMParser` instantiation in `<sl-icon>` to better support SSR [#778](https://github.com/shoelace-style/shoelace/issues/778)
- Reverted menu item caching due to regression [#766](https://github.com/shoelace-style/shoelace/issues/766)
- Updated Floating UI to 0.5.2

## 2.0.0-beta.74

- 🚨 BREAKING: reworked focus rings to use outlines instead of box shadows
  - Removed the `--sl-focus-ring-alpha` design token
  - Refactored `--sl-focus-ring` to be an `outline` property instead of a `box-shadow` property
  - Added `--sl-focus-ring-color`, `--sl-focus-ring-style`, and `--sl-focus-ring-offset`
- 🚨 BREAKING: removed `variant` from `<sl-radio-button>`
- Added `sl-label-change` event to `<sl-menu-item>`
- Added `blur()`, `click()`, and `focus()` methods as well as `sl-blur` and `sl-focus` events to `<sl-icon-button>` [#730](https://github.com/shoelace-style/shoelace/issues/730)
- Added Tabler Icons example to icons page
- Fixed a bug where updating a menu item's label wouldn't update the display label in `<sl-select>` [#729](https://github.com/shoelace-style/shoelace/issues/729)
- Fixed a bug where the FormData event polyfill was causing issues with older browsers [#747](https://github.com/shoelace-style/shoelace/issues/747)
- Fixed a bug that caused a console error when setting `value` to `null` or `undefined` in `<sl-input>`, `<sl-select>`, and `<sl-textarea>` [#751](https://github.com/shoelace-style/shoelace/pull/751)
- Fixed a bug that caused `<sl-checkbox>` and `<sl-radio>` controls without a `value` to submit as `null` instead of `on` like native inputs [#744](https://github.com/shoelace-style/shoelace/issues/744)
- Fixed a bug that caused `<sl-dropdown>` and dependent components to add unexpected padding around the panel [#743](https://github.com/shoelace-style/shoelace/issues/743)
- Fixed a bug that prevented `valueAsDate` and `valueAsNumber` from updating synchronously [#760](https://github.com/shoelace-style/shoelace/issues/760)
- Fixed a bug that caused `<sl-menu-item>` to load icons from the default library instead of the system library [#765](https://github.com/shoelace-style/shoelace/issues/765)
- Fixed a bug in `<sl-input>` that prevented a canceled `keydown` event from submitting the containing form when pressing enter [#764](https://github.com/shoelace-style/shoelace/issues/764)
- Improved behavior of clearable and password toggle buttons in `<sl-input>` and `<sl-select>` [#745](https://github.com/shoelace-style/shoelace/issues/745)
- Improved performance of `<sl-select>` by caching menu items instead of traversing for them each time
- Improved drag utility so initial click/touch events can be accepted [#758](https://github.com/shoelace-style/shoelace/issues/758)
- Improved `<sl-color-picker>` to use an HSB grid instead of HSL to be more consistent with existing color picker implementations [#762](https://github.com/shoelace-style/shoelace/issues/762)
- Improved `<sl-color-picker>` so the cursor is hidden and the preview is larger when dragging the grid
- Refactored `<sl-menu>` to be more performant by caching menu items on slot change
- Reverted form submit logic [#718](https://github.com/shoelace-style/shoelace/issues/718)
- Updated the `disabled` attribute so it reflects in `<sl-dropdown>` [#741](https://github.com/shoelace-style/shoelace/discussions/741)
- Updated the `name` and `icon` attribute so they reflect in `<sl-icon>` [#742](https://github.com/shoelace-style/shoelace/pull/742)
- Updated Lit to 2.2.5
- Updated Bootstrap Icons to 1.8.3
- Updated TypeScript to 4.7.2
- Updated esbuild to 0.14.40
- Updated all other dependencies to latest versions

## 2.0.0-beta.73

- Added `button` part to `<sl-radio-button>`
- Added custom validity examples and tests to `<sl-checkbox>`, `<sl-radio>`, and `<sl-radio-button>`
- Added `enterkeyhint` attribute to `<sl-input>` and `<sl-textarea>`
- Fixed a bug that prevented `setCustomValidity()` from working with `<sl-radio-button>`
- Fixed a bug where the right border of a checked `<sl-radio-button>` was the wrong color
- Fixed a bug that prevented a number of properties, methods, etc. from being documented in `<sl-radio>` and `<sl-radio-button>`
- Fixed a bug in `<sl-avatar>` that prevented valid images from showing after an invalid or missing image was provided [#717](https://github.com/shoelace-style/shoelace/issues/717)
- Fixed a bug that resulted in a console error being thrown on keydown in `<sl-dropdown>` [#719](https://github.com/shoelace-style/shoelace/issues/719)
- Fixed a bug that prevented `<sl-dropdown>` from being closed when opened initially [#720](https://github.com/shoelace-style/shoelace/issues/720)
- Fixed a bug that caused the test runner to fail when using a locale other than en-US [#726](https://github.com/shoelace-style/shoelace/issues/726)
- Improved form submit logic so most user-added event listeners will run after form data is attached and validation occurs [#718](https://github.com/shoelace-style/shoelace/issues/718)
- Improved accessibility of `<sl-tooltip>` so screen readers announce the content on hover/focus [#219](https://github.com/shoelace-style/shoelace/issues/219)
- Improved accessibility of form controls by exposing clear buttons and password visibility buttons to screen readers while keeping them out of the tab order [#727](https://github.com/shoelace-style/shoelace/issues/727)
- Updated `<sl-tab-group>` and `<sl-menu>` to cycle through tabs and menu items instead of stopping at the first/last when using the keyboard
- Removed path aliasing (again) because it doesn't work with Web Test Runner's esbuild plugin

## 2.0.0-beta.72

- 🚨 BREAKING: refactored parts in `<sl-input>`, `<sl-range>`, `<sl-select>`, and `<sl-textarea>` to allow you to customize the label and help text position
  - Added `form-control-input` part
  - Renamed `label` to `form-control-label`
  - Renamed `help-text` to `form-control-help-text`
- 🚨 BREAKING: removed status from the `sl-error` event payload in `<sl-icon>`
- Added the experimental `<sl-radio-button>` component
- Added `button-group` and `button-group__base` parts to `<sl-radio-group>`
- Added the `label` attribute and slot to `<sl-color-picker>` to improve accessibility with screen readers
- Fixed a bug that prevented form submission from working as expected in some cases
- Fixed a bug that prevented `<sl-split-panel>` from toggling `vertical` properly [#703](https://github.com/shoelace-style/shoelace/issues/703)
- Fixed a bug that prevented `<sl-color-picker>` from rendering a color initially [#704](https://github.com/shoelace-style/shoelace/issues/704)
- Fixed a bug that caused focus trapping to fail when used inside a shadow root [#709](https://github.com/shoelace-style/shoelace/issues/709)
- Improved accessibility throughout the docs
- Improved accessibility of `<sl-dropdown>` so the trigger's expanded state is announced correctly
- Improved accessibility of `<sl-format-date>` but rendering a `<time>` element instead of plain text
- Improved accessibility of `<sl-select>` so disabled controls announce correct
- Improved accessibility in `<sl-tag>` so remove buttons have labels
- Refactored `<sl-radio>` to move selection logic into `<sl-radio-group>`
- Updated slot detection logic so it ignores visually hidden elements
- Upgraded the status of `<sl-visually-hidden>` from experimental to stable

## 2.0.0-beta.71

- 🚨 BREAKING: refactored exported parts to ensure composed components and their parts can be targeted via CSS
  - Refactored the `eye-dropper-button` part and added `eye-dropper-button__base`, `eye-dropper-button__prefix`, `eye-dropper-button__label`, `eye-dropper-button__suffix`, and `eye-dropper-button__caret` parts to `<sl-color-picker>`
  - Refactored the `format-button` part and added `format-button__base`, `format-button__prefix`, `format-button__label`, `format-button__suffix`, and `format-button__caret` parts to `<sl-color-picker>`
  - Moved the `close-button` part in `<sl-alert>` to the internal `<sl-icon-button>` and removed the `<span>` that wrapped it
  - Moved the `close-button` part in `<sl-dialog>` and `<sl-drawer>` to point to the host element and added the `close-button__base` part
  - Renamed parts in `<sl-select>` from `tag-base` to `tag__base`, `tag-content` to `tag__content`, and `tag-remove-button` to `tag__remove-button`
  - Moved the `close-button` part in `<sl-tab>` to the internal `<sl-icon-button>` and added the `close-button__base` part
  - Moved the `scroll-button` part in `<sl-tab-group>` to the internal `<sl-icon-button>` and added the `scroll-button__base`, `scroll-button--start`, and `scroll-button--end` parts
  - Moved the `remove-button` part in `<sl-tag>` to the internal `<sl-icon-button>` and added the `remove-button__base` part
- 🚨 BREAKING: removed `checked-icon` part from `<sl-menu-item>` in preparation for parts refactor
- 🚨 BREAKING: changed the `typeToSelect()` method's argument from `String` to `KeyboardEvent` in `<sl-menu>` to support more advanced key combinations
- Added `form`, `formaction`, `formmethod`, `formnovalidate`, and `formtarget` attributes to `<sl-button>` [#699](https://github.com/shoelace-style/shoelace/issues/699)
- Added Prettier and ESLint to markdown files
- Added background color and border to `<sl-menu>`
- Added more tests for `<sl-input>`, `<sl-select>`, and `<sl-textarea>`
- Fixed a bug that prevented forms from submitting when pressing <kbd>Enter</kbd> inside of an `<sl-input>` [#700](https://github.com/shoelace-style/shoelace/issues/700)
- Fixed a bug in `<sl-input>` that prevented the `valueAsDate` and `valueAsNumber` properties from working when set before the component was initialized
- Fixed a bug in `<sl-dropdown>` where pressing <kbd>Home</kbd> or <kbd>End</kbd> wouldn't select the first or last menu items, respectively
- Improved `autofocus` behavior in Safari for `<sl-dialog>` and `<sl-drawer>` [#693](https://github.com/shoelace-style/shoelace/issues/693)
- Improved type to select logic in `<sl-menu>` so it supports <kbd>Backspace</kbd> and gives users more time before resetting
- Improved checkmark size and positioning in `<sl-menu-item>`
- Improved accessibility in form controls that have help text so they're announced correctly in various screen readers
- Removed feature detection for `focus({ preventScroll })` since it no longer works in Safari
- Removed the `--sl-tooltip-arrow-start-end-offset` design token
- Removed the `pattern` attribute from `<sl-textarea>` as it was documented incorrectly and never supported
- Replaced Popper positioning dependency with Floating UI in `<sl-dropdown>` and `<sl-tooltip>`

## 2.0.0-beta.70

- Added `tag-base`, `tag-content`, and `tag-remove-button` parts to `<sl-select>` [#682](https://github.com/shoelace-style/shoelace/discussions/682)
- Added support for focusing elements with `autofocus` when `<sl-dialog>` and `<sl-drawer>` open [#688](https://github.com/shoelace-style/shoelace/issues/688)
- Added the `placement` attribute to `<sl-select>` [#687](https://github.com/shoelace-style/shoelace/pull/687)
- Added Danish translation [#690](https://github.com/shoelace-style/shoelace/pull/690)
- Fixed a bug that allowed `<sl-dropdown>` to go into an incorrect state when activating the trigger while disabled [#684](https://github.com/shoelace-style/shoelace/pull/684)
- Fixed a bug where Safari would sometimes not focus after preventing `sl-initial-focus` [#688](https://github.com/shoelace-style/shoelace/issues/688)
- Fixed a bug where the active tab indicator in `<sl-tab-group>` would be misaligned when using disabled tabs [#695](https://github.com/shoelace-style/shoelace/pull/695)
- Improved the size of the remove button in `<sl-tag>`
- Removed Google Analytics from the docs

## 2.0.0-beta.69

- Added `web-types.json` to improve the dev experience for WebStorm/PHPStorm users [#328](https://github.com/shoelace-style/shoelace/issues/328)
- Fixed a bug that caused an error when pressing up/down in `<sl-select>`
- Fixed a bug that caused `<sl-details>` to not show when double clicking the summary while open [#662](https://github.com/shoelace-style/shoelace/issues/662)
- Fixed a bug that prevented the first/last menu item from receiving focus when pressing up/down in `<sl-dropdown>`
- Fixed a bug that caused the active tab indicator in `<sl-tab-group>` to render incorrectly when used inside an element that animates [#671](https://github.com/shoelace-style/shoelace/pull/671)
- Fixed a bug that allowed values in `<sl-range>` to be invalid according to its `min|max|step` [#674](https://github.com/shoelace-style/shoelace/issues/674)
- Updated Lit to 2.1.4
- Updated all other dependencies to latest versions

## 2.0.0-beta.68

- Fixed path aliases in generated files so they're relative again [#669](https://github.com/shoelace-style/shoelace/pull/669)

## 2.0.0-beta.67

- Fixed a TypeScript config regression introduced in [#647](https://github.com/shoelace-style/shoelace/pull/647) that removed the `rootDir`, breaking the expected build output

## 2.0.0-beta.66

- Attempted to fix a bug that prevented types from being generated in the build

## 2.0.0-beta.65

- 🚨 BREAKING: the `unit` property of `<sl-format-bytes>` has changed to `byte | bit` instead of `bytes | bits`
- Added `display-label` part to `<sl-select>` [#650](https://github.com/shoelace-style/shoelace/issues/650)
- Added `--spacing` custom property to `<sl-divider>` [#664](https://github.com/shoelace-style/shoelace/pull/664)
- Added `event.detail.source` to the `sl-request-close` event in `<sl-dialog>` and `<sl-drawer>`
- Fixed a bug that caused `<sl-progress-ring>` to render the wrong size when `--track-width` was increased [#656](https://github.com/shoelace-style/shoelace/issues/656)
- Fixed a bug that allowed `<sl-details>` to open and close when disabled using a screen reader [#658](https://github.com/shoelace-style/shoelace/issues/658)
- Fixed a bug in the FormData event polyfill that threw an error in some environments [#666](https://github.com/shoelace-style/shoelace/issues/666)
- Implemented stricter linting to improve consistency and reduce errors, which resulted in many small refactors throughout the codebase [#647](https://github.com/shoelace-style/shoelace/pull/647)
- Improved accessibility of `<sl-dialog>` and `<sl-drawer>` by making the title an `<h2>` and adding a label to the close button
- Improved search results in the documentation
- Refactored `<sl-format-byte>` to use `Intl.NumberFormat` so it supports localization
- Refactored themes so utility styles are no longer injected as `<style>` elements to support stricter CSP rules [#571](https://github.com/shoelace-style/shoelace/issues/571)
- Restored the nicer animation on `<sl-spinner>` and verified it works in Safari
- Updated Feather icon example to use Lucide [#657](https://github.com/shoelace-style/shoelace/issues/657)
- Updated minimum Node version to 14.17
- Updated Lit to 2.1.2
- Updated to Bootstrap Icons to 1.8.1
- Updated all other dependencies to latest versions

## 2.0.0-beta.64

- 🚨 BREAKING: removed `<sl-form>` because all form components submit with `<form>` now ([learn more](/getting-started/form-controls))
- 🚨 BREAKING: changed `submit` attribute to `type="submit"` on `<sl-button>`
- 🚨 BREAKING: changed the `alt` attribute to `label` in `<sl-avatar>` for consistency with other components
- Added `role="status"` to `<sl-spinner>`
- Added `valueAsDate` and `valueAsNumber` properties to `<sl-input>` [#570](https://github.com/shoelace-style/shoelace/issues/570)
- Added `start`, `end`, and `panel` parts to `<sl-split-panel>` [#639](https://github.com/shoelace-style/shoelace/issues/639)
- Fixed broken spinner animation in Safari [#633](https://github.com/shoelace-style/shoelace/issues/633)
- Fixed an a11y bug in `<sl-tooltip>` where `aria-describedby` referenced an id in the shadow root
- Fixed a bug in `<sl-radio>` where tabbing didn't work properly in Firefox [#596](https://github.com/shoelace-style/shoelace/issues/596)
- Fixed a bug in `<sl-input>` where clicking the left/right edge of the control wouldn't focus it
- Fixed a bug in `<sl-input>` where autofill had strange styles [#644](https://github.com/shoelace-style/shoelace/pull/644)
- Improved `<sl-spinner>` track color when used on various backgrounds
- Improved a11y in `<sl-radio>` so VoiceOver announces radios properly in a radio group
- Improved the API for the experimental `<sl-split-panel>` component by making `position` accept a percentage and adding the `position-in-pixels` attribute
- Refactored `<sl-breadcrumb-item>`, `<sl-button>`, `<sl-card>`, `<sl-dialog>`, `<sl-drawer>`, `<sl-input>`, `<sl-range>`, `<sl-select>`, and `<sl-textarea>` to use a Reactive Controller for slot detection
- Refactored internal id usage in `<sl-details>`, `<sl-dialog>`, `<sl-drawer>`, and `<sl-dropdown>`
- Removed `position: relative` from the common component stylesheet
- Updated Lit to 2.1.0
- Updated all other dependencies to latest versions

## 2.0.0-beta.63

- 🚨 BREAKING: changed the `type` attribute to `variant` in `<sl-alert>`, `<sl-badge>`, `<sl-button>`, and `<sl-tag>` since it's more appropriate and to disambiguate from other `type` attributes
- 🚨 BREAKING: removed `base` part from `<sl-divider>` to simplify the styling API
- Added the experimental `<sl-split-panel>` component
- Added `focus()` and `blur()` methods to `<sl-select>` [#625](https://github.com/shoelace-style/shoelace/pull/625)
- Fixed a bug where setting `tooltipFormatter` on `<sl-range>` in JSX causes React@experimental to error out
- Fixed a bug where clicking on a slotted icon in `<sl-button>` wouldn't submit forms [#626](https://github.com/shoelace-style/shoelace/issues/626)
- Added the `sl-` prefix to generated ids for `<sl-tab>` and `<sl-tab-panel>`
- Refactored `<sl-button>` to use Lit's static expressions to reduce code
- Simplified `<sl-spinner>` animation

## 2.0.0-beta.62

- 🚨 BREAKING: changed the `locale` attribute to `lang` in `<sl-format-bytes>`, `<sl-format-date>`, `<sl-format-number>`, and `<sl-relative-time>` to be consistent with how localization is handled
- Added localization support including translations for English, German, German (Switzerland), Spanish, French, Hebrew, Japanese, Dutch, Polish, Portuguese, and Russian translations [#419](https://github.com/shoelace-style/shoelace/issues/419)
- CodePen examples will now open in light or dark depending on your current preference
- Fixed a bug where tag names weren't being generated in `vscode.html-custom-data.json` [#593](https://github.com/shoelace-style/shoelace/pull/593)
- Fixed a bug in `<sl-tooltip>` where the tooltip wouldn't reposition when content changed
- Fixed a bug in `<sl-select>` where focusing on a filled control showed the wrong focus ring
- Fixed a bug where setting `value` initially on `<sl-color-picker>` didn't work in React [#602](https://github.com/shoelace-style/shoelace/issues/602)
- Updated filled inputs to have the same appearance when focused
- Updated `color` dependency from 3.1.3 to 4.0.2
- Updated `<sl-format-bytes>`, `<sl-format-date>`, `<sl-format-number>`, and `<sl-relative-time>` to work like other localized components
- Upgraded the status of `<sl-qr-code>` from experimental to stable
- Updated to Bootstrap Icons to 1.7.2
- Upgraded color to 4.1.0

## 2.0.0-beta.61

This release improves the dark theme by shifting luminance in both directions, slightly condensing the spectrum. This results in richer colors in dark mode. It also reduces theme stylesheet sizes by eliminating superfluous gray palette variations.

In [beta.48](#_200-beta48), I introduced a change to color tokens that allowed you to access alpha values at the expense of a verbose, non-standard syntax. After considering feedback from the community, I've decided to revert this change so the `rgb()` function is no longer required. Many users reported never using it for alpha, and even more reported having trouble remembering to use `rgb()` and that it was causing more harm than good.

Furthermore, both Safari and Firefox have implemented [`color-mix()`](<https://developer.mozilla.org/en-US/docs/Web/CSS/color_value/color-mix()>) behind a flag, so access to alpha channels and other capabilities are coming to the browser soon.

If you're using color tokens in your own stylesheet, simply remove the `rgb()` to update to this version.

```css
.your-styles {
  /* change this */
  color: rgb(var(--sl-color-primary-500));

  /* to this */
  color: var(--sl-color-primary-500);
}
```

Thank you for your help and patience with testing Shoelace. I promise, we're not far from a stable release!

- 🚨 BREAKING: removed blue gray, cool gray, true gray, and warm gray color palettes
- 🚨 BREAKING: removed `--sl-focus-ring-color`, and `--sl-focus-ring-alpha` (use `--sl-focus-ring` instead)
- 🚨 BREAKING: removed `--sl-surface-base` and `--sl-surface-base-alt` tokens (use the neutral palette instead)
- Added experimental `<sl-visually-hidden>` component
- Added `clear-icon` slot to `<sl-select>` [#591](https://github.com/shoelace-style/shoelace/issues/591)
- Fixed a bug in `<sl-progress-bar>` where the label would show in the default slot
- Improved the dark theme palette so colors are bolder and don't appear washed out
- Improved a11y of `<sl-avatar>` by representing it as an image with an `alt` [#579](https://github.com/shoelace-style/shoelace/issues/579)
- Improved a11y of the scroll buttons in `<sl-tab-group>`
- Improved a11y of the close button in `<sl-tab>`
- Improved a11y of `<sl-tab-panel>` by removing an invalid `aria-selected` attribute [#579](https://github.com/shoelace-style/shoelace/issues/579)
- Improved a11y of `<sl-icon>` by not using a variation of the `name` attribute for labels (use the `label` prop instead)
- Moved `role` from the shadow root to the host element in `<sl-menu>`
- Removed redundant `role="menu"` in `<sl-dropdown>`
- Slightly faster animations for showing and hiding `<sl-dropdown>`
- Updated to Bootstrap Icons to 1.7.1
- Upgraded the status of `<sl-mutation-observer>` from experimental to stable

## 2.0.0-beta.60

- Added React examples and CodePen links to all components
- Changed the `attr` in experimental `<sl-mutation-observer>` to require `"*"` instead of `""` to target all attributes
- Fixed a bug in `<sl-progress-bar>` where the `label` attribute didn't set the label
- Fixed a bug in `<sl-rating>` that caused disabled and readonly controls to transition on hover
- The `panel` property of `<sl-tab>` is now reflected
- The `name` property of `<sl-tab-panel>` is now reflected

## 2.0.0-beta.59

- Added React wrappers as first-class citizens
- Added eye dropper to `<sl-color-picker>` when the browser supports the [EyeDropper API](https://wicg.github.io/eyedropper-api/)
- Fixed a bug in `<sl-button-group>` where buttons groups with only one button would have an incorrect border radius
- Improved the `<sl-color-picker>` trigger's border in dark mode
- Switched clearable icon from `x-circle` to `x-circle-fill` to make it easier to recognize
- Updated to Bootstrap Icons to 1.7.0
- Updated to Lit 2.0.2

## 2.0.0-beta.58

This version once again restores the bundled distribution because the unbundled + CDN approach is currently confusing and [not working properly](https://github.com/shoelace-style/shoelace/issues/559#issuecomment-949662331). Unbundling the few dependencies Shoelace has is still a goal of the project, but [this jsDelivr bug](https://github.com/jsdelivr/jsdelivr/issues/18337) needs to be resolved before we can achieve it.

I sincerely apologize for the instability of the last few beta releases as a result of this effort.

- Added experimental `<sl-animated-image>` component
- Added `label` attribute to `<sl-progress-bar>` and `<sl-progress-ring>` to improve a11y
- Fixed a bug where the tooltip would show briefly when clicking a disabled `<sl-range>`
- Fixed a bug that caused a console error when `<sl-range>` was used
- Fixed a bug where the `nav` part in `<sl-tab-group>` was on the incorrect element [#563](https://github.com/shoelace-style/shoelace/pull/563)
- Fixed a bug where non-integer aspect ratios were calculated incorrectly in `<sl-responsive-media>`
- Fixed a bug in `<sl-range>` where setting `value` wouldn't update the active and inactive portion of the track [#572](https://github.com/shoelace-style/shoelace/pull/572)
- Reverted to publishing the bundled dist and removed `/+esm` links from the docs
- Updated to Bootstrap Icons to 1.6.1

## 2.0.0-beta.57

- Fix CodePen links and CDN links

## 2.0.0-beta.56

This release is the second attempt at unbundling dependencies. This will be a breaking change only if your configuration _does not_ support bare module specifiers. CDN users and bundler users will be unaffected, but note the URLs for modules on the CDN must have the `/+esm` now.

- Added the `hoist` attribute to `<sl-tooltip>` [#564](https://github.com/shoelace-style/shoelace/issues/564)
- Unbundled dependencies and configured external imports to be packaged with bare module specifiers

## 2.0.0-beta.55

- Revert unbundling due to issues with the CDN not handling bare module specifiers as expected

## 2.0.0-beta.54

Shoelace doesn't have a lot of dependencies, but this release unbundles most of them so you can potentially save some extra kilobytes. This will be a breaking change only if your configuration _does not_ support bare module specifiers. CDN users and bundler users will be unaffected.

- 🚨 BREAKING: renamed the `sl-clear` event to `sl-remove`, the `clear-button` part to `remove-button`, and the `clearable` property to `removable` in `<sl-tag>`
- Added the `disabled` prop to `<sl-resize-observer>`
- Fixed a bug in `<sl-mutation-observer>` where setting `disabled` initially didn't work
- Unbundled dependencies and configured external imports to be packaged with bare module specifiers

## 2.0.0-beta.53

- 🚨 BREAKING: removed `<sl-menu-divider>` (use `<sl-divider>` instead)
- 🚨 BREAKING: removed `percentage` attribute from `<sl-progress-bar>` and `<sl-progress-ring>` (use `value` instead)
- 🚨 BREAKING: switched the default `type` of `<sl-tag>` from `primary` to `neutral`
- Added the experimental `<sl-mutation-observer>` component
- Added the `<sl-divider>` component
- Added `--sl-color-neutral-0` and `--sl-color-neutral-50` as early surface tokens to improve the appearance of alert, card, and panels in dark mode
- Added the `--sl-panel-border-width` design token
- Added missing background color to `<sl-details>`
- Added the `--padding` custom property to `<sl-tab-panel>`
- Added the `outline` variation to `<sl-button>` [#522](https://github.com/shoelace-style/shoelace/issues/522)
- Added the `filled` variation to `<sl-input>`, `<sl-textarea>`, and `<sl-select>` and supporting design tokens
- Added the `control` part to `<sl-select>` so you can target the main control with CSS [#538](https://github.com/shoelace-style/shoelace/issues/538)
- Added a border to `<sl-badge>` to improve contrast when drawn on various background colors
- Added `--track-color-active` and `--track-color-inactive` custom properties to `<sl-range>` [#550](https://github.com/shoelace-style/shoelace/issues/550)
- Added the undocumented custom properties `--thumb-size`, `--tooltip-offset`, `--track-height` on `<sl-range>`
- Changed the default `distance` in `<sl-dropdown>` from `2` to `0` [#538](https://github.com/shoelace-style/shoelace/issues/538)
- Fixed a bug where `<sl-select>` would be larger than the viewport when it had lots of options [#544](https://github.com/shoelace-style/shoelace/issues/544)
- Fixed a bug where `<sl-progress-ring>` wouldn't animate in Safari
- Updated the default height of `<sl-progress-bar>` from `16px` to `1rem` and added a subtle shadow to indicate depth
- Removed the `lit-html` dependency and moved corresponding imports to `lit` [#546](https://github.com/shoelace-style/shoelace/issues/546)

## 2.0.0-beta.52

- 🚨 BREAKING: changed the `--stroke-width` custom property of `<sl-spinner>` to `--track-width` for consistency
- 🚨 BREAKING: removed the `size` and `stroke-width` attributes from `<sl-progress-ring>` so it's fully customizable with CSS (use the `--size` and `--track-width` custom properties instead)
- Added the `--speed` custom property to `<sl-spinner>`
- Added the `--size` and `--track-width` custom properties to `<sl-progress-ring>`
- Added tests for `<sl-badge>` [#530](https://github.com/shoelace-style/shoelace/pull/530)
- Fixed a bug where `<sl-tab>` wasn't using a border radius token [#523](https://github.com/shoelace-style/shoelace/issues/523)
- Fixed a bug in the Remix Icons example where some icons would 404 [#528](https://github.com/shoelace-style/shoelace/issues/528)
- Updated `<sl-progress-ring>` to use only CSS for styling
- Updated `<sl-spinner>` to use an SVG and improved the indicator animation
- Updated to Lit 2.0 and lit-html 2.0 🔥

## 2.0.0-beta.51

A number of users had trouble counting characters that repeat, so this release improves design token patterns so that "t-shirt sizes" are more accessible. For example, `--sl-font-size-xxx-large` has become `--sl-font-size-3x-large`. This change applies to all design tokens that use this scale.

- 🚨 BREAKING: all t-shirt size design tokens now use `2x`, `3x`, `4x` instead of `xx`, `xxx`, `xxxx`
- Added missing `--sl-focus-ring-*` tokens to dark theme
- Added an "Importing" section to all components with copy/paste code to make cherry picking easier
- Improved the documentation search with a custom plugin powered by [Lunr](https://lunrjs.com/)
- Improved the `--sl-shadow-x-small` elevation
- Improved visibility of elevations and overlays in dark theme
- Reduced the size of `<sl-color-picker>` slightly to better accommodate mobile devices
- Removed `<sl-icon>` dependency from `<sl-color-picker>` and improved the copy animation

## 2.0.0-beta.50

- Added `<sl-breadcrumb>` and `<sl-breadcrumb-item>` components
- Added `--sl-letter-spacing-denser`, `--sl-letter-spacing-looser`, `--sl-line-height-denser`, and `--sl-line-height-looser` design tokens
- Fixed a bug where form controls would error out when the value was set to `undefined` [#513](https://github.com/shoelace-style/shoelace/pull/513)

## 2.0.0-beta.49

This release changes the way focus states are applied to elements. In browsers that support [`:focus-visible`](https://developer.mozilla.org/en-US/docs/Web/CSS/:focus-visible), it will be used. In unsupportive browsers ([currently only Safari](https://caniuse.com/mdn-css_selectors_focus-visible)), `:focus` will be used instead. This means the browser will determine whether a focus ring should be shown based on how the user interacts with the page.

This release also fixes a critical bug in the color scale where `--sl-color-neutral-0` and `--sl-color-neutral-1000` were reversed.

- 🚨 BREAKING: fixed a bug where `--sl-color-neutral-0` and `--sl-color-neutral-1000` were inverted (swap them to update)
- 🚨 BREAKING: removed the `no-fieldset` property from `<sl-radio-group>` (fieldsets are now hidden by default; use `fieldset` to show them)
- 🚨 BREAKING: removed `--focus-ring` custom property from `<sl-input>`, `<sl-select>`, `<sl-tab>` for consistency with other form controls
- Added `--swatch-size` custom property to `<sl-color-picker>`
- Added `date` to `<sl-input>` as a supported `type`
- Added the `--sl-focus-ring` design token for a more convenient way to apply focus ring styles
- Adjusted elevation tokens to use neutral in light mode and black in dark mode
- Adjusted `--sl-overlay-background-color` in dark theme to be black instead of gray
- Fixed a bug in `<sl-color-picker>` where the opacity slider wasn't showing the current color
- Fixed a bug where Edge in Windows would show the native password toggle next to the custom password toggle [#508](https://github.com/shoelace-style/shoelace/issues/508)
- Fixed a bug where pressing up/down in `<sl-tab-group>` didn't select the next/previous tab in vertical placements
- Improved size of `<sl-color-picker>`
- Improved icon contrast in `<sl-input>`
- Improved contrast of `<sl-switch>`
- Improved `:focus-visible` behavior in many components
- Removed elevation from `<sl-color-picker>` when rendered inline
- Removed custom `:focus-visible` logic in favor of a directive that outputs `:focus-visible` or `:focus` depending on browser support
- Updated to Lit 2.0.0-rc.3
- Updated to lit-html 2.0.0-rc.4

## 2.0.0-beta.48

This release improves theming by offering both light and dark themes that can be used autonomously. It also improves contrast in most components, adds a variety of new color primitives, and changes the way color tokens are consumed.

Previously, color tokens were in hexadecimal format. Now, Shoelace now uses an `R G B` format that requires you to use the `rgb()` function in your CSS.

```css
.example {
  /* rgb() is required now */
  color: var(--sl-color-neutral-500);
}
```

This is more verbose than previous versions, but it has the advantage of letting you set the alpha channel of any color token.

```css
.example-with-alpha {
  /* easily adjust opacity for any color token */
  color: rgb(var(--sl-color-neutral-500) / 50%);
}
```

This change applies to all design tokens that implement a color. Refer to the [color tokens](/tokens/color) page for more details.

- 🚨 BREAKING: all design tokens that implement colors have been converted to `R G B` and must be used with the `rgb()` function
- 🚨 BREAKING: removed `--sl-color-black|white` color tokens (use `--sl-color-neutral-0|1000` instead)
- 🚨 BREAKING: removed `--sl-color-primary|success|warning|info|danger-text` design tokens (use theme or primitive colors instead)
- 🚨 BREAKING: removed `info` variant from `<sl-alert>`, `<sl-badge>`, `<sl-button>`, and `<sl-tag>` (use `neutral` instead)
- 🚨 BREAKING: removed `--sl-color-info-*` design token (use `--sl-color-neutral-*` instead)
- 🚨 BREAKING: renamed `dist/themes/base.css` to `dist/themes/light.css`
- 🚨 BREAKING: removed `--sl-focus-ring-color-primary` tokens (use color tokens and `--sl-focus-ring-width|alpha` instead)
- 🚨 BREAKING: removed `--tabs-border-color` from `<sl-tab-group>` (use `--track-color` instead)
- 🚨 BREAKING: changed the default value for `effect` to `none` in `<sl-skeleton>` (use `sheen` to restore the original behavior)
- Added new color primitives to the base set of design tokens
- Added `--sl-color-*-950` swatches to all color palettes
- Added a console error that appears when menu items have duplicate values in `<sl-select>`
- Added CodePen link to code examples
- Added `prefix` and `suffix` slots to `<sl-select>` [#501](https://github.com/shoelace-style/shoelace/pull/501)
- Added `--indicator-color` custom property to `<sl-tab-group>`
- Exposed base and dark stylesheets so they can be imported via JavaScript [#438](https://github.com/shoelace-style/shoelace/issues/438)
- Fixed a bug in `<sl-menu>` where pressing <kbd>Enter</kbd> after using type to select would result in the wrong value
- Fixed a bug in `<sl-radio-group>` where clicking a radio button would cause the wrong control to be focused
- Fixed a bug in `<sl-button>` and `<sl-icon-button>` where an unintended `ref` attribute was present
- Fixed a bug in the focus-visible utility that failed to respond to mouseup events
- Fixed a bug where clicking on a menu item would persist its hover/focus state
- Fixed a bug in `<sl-select>` where it would erroneously intercept important keyboard shortcuts [#504](https://github.com/shoelace-style/shoelace/issues/504)
- Improved contrast throughout all components [#128](https://github.com/shoelace-style/shoelace/issues/128)
- Refactored thumb position logic in `<sl-switch>` [#490](https://github.com/shoelace-style/shoelace/pull/490)
- Reworked the dark theme to use an inverted + shifted design token approach instead of component-specific selectors

## 2.0.0-beta.47

This release improves how component dependencies are imported. If you've been cherry picking, you no longer need to import component dependencies manually. This significantly improves developer experience, making Shoelace even easier to use. For transparency, component dependencies will continue to be listed in the docs.

- Added "Reflects" column to the properties table
- Dependencies are now automatically imported for all components
- Fixed a bug where tabbing into `<sl-radio-group>` would not always focus the checked radio
- Fixed a bug in component styles that prevented the box sizing reset from being applied
- Fixed a regression in `<sl-color-picker>` where dragging the grid handle wasn't smooth
- Fixed a bug where slot detection could incorrectly match against slots of child elements [#481](https://github.com/shoelace-style/shoelace/pull/481)
- Fixed a bug in `<sl-input>` where focus would move to the end of the input when typing in Safari [#480](https://github.com/shoelace-style/shoelace/issues/480)
- Improved base path utility logic

## 2.0.0-beta.46

This release improves the developer experience of `<sl-animation>`. Previously, an animation was assumed to be playing unless the `pause` attribute was set. This behavior has been reversed and `pause` has been removed. Now, animations will not play until the new `play` attribute is applied.

This is a lot more intuitive and makes it easier to activate animations imperatively. In addition, the `play` attribute is automatically removed automatically when the animation finishes or cancels, making it easier to restart finite animations. Lastly, the animation's timing is now accessible through the new `currentTime` property instead of `getCurrentTime()` and `setCurrentTime()`.

In addition, Shoelace no longer uses Sass. Component styles now use Lit's template literal styles and theme files use pure CSS.

- 🚨 BREAKING: removed the `pause` attribute from `<sl-animation>` (use `play` to start and stop the animation instead)
- 🚨 BREAKING: removed `getCurrentTime()` and `setCurrentTime()` from `<sl-animation>` (use the `currentTime` property instead)
- 🚨 BREAKING: removed the `close-on-select` attribute from `<sl-dropdown>` (use `stay-open-on-select` instead)
- Added the `currentTime` property to `<sl-animation>` to control the current time without methods
- Fixed a bug in `<sl-range>` where the tooltip wasn't showing in Safari [#477](https://github.com/shoelace-style/shoelace/issues/477)
- Fixed a bug in `<sl-menu>` where pressing <kbd>Enter</kbd> in a menu didn't work with click handlers
- Reworked `<sl-menu>` and `<sl-menu-item>` to use a roving tab index and improve keyboard accessibility
- Reworked tabbable logic to be more performant [#466](https://github.com/shoelace-style/shoelace/issues/466)
- Switched component stylesheets from Sass to Lit's template literal styles
- Switched theme stylesheets from Sass to CSS

## 2.0.0-beta.45

This release changes the way component metadata is generated. Previously, the project used TypeDoc to analyze components and generate a very large file with type data. The data was then parsed and converted to an easier-to-consume file called `metadata.json`. Alas, TypeDoc is expensive to run and the metadata format wasn't standard.

Thanks to an amazing effort by [Pascal Schilp](https://twitter.com/passle_), the world has a simpler, faster way to gather metadata using the [Custom Elements Manifest Analyzer](https://github.com/open-wc/custom-elements-manifest). Not only is this tool faster, but the data follows the evolving `custom-elements.json` format. This is exciting because a standard format for custom elements opens the door for many potential uses, including documentation generation, framework adapters, IDE integrations, third-party uses, and more. [Check out Pascal's great article](https://dev.to/open-wc/introducing-custom-elements-manifest-gkk) for more info about `custom-elements.json` and the new analyzer.

The docs have been updated to use the new `custom-elements.json` file. If you're relying on the old `metadata.json` file for any purpose, this will be a breaking change for you.

- 🚨 BREAKING: removed the `sl-overlay-click` event from `<sl-dialog>` and `<sl-drawer>` (use `sl-request-close` instead) [#471](https://github.com/shoelace-style/shoelace/discussions/471)
- 🚨 BREAKING: removed `metadata.json` (use `custom-elements.json` instead)
- Added `custom-elements.json` for component metadata
- Added `sl-request-close` event to `<sl-dialog>` and `<sl-drawer>`
- Added `dialog.denyClose` and `drawer.denyClose` animations
- Fixed a bug in `<sl-color-picker>` where setting `value` immediately wouldn't trigger an update
- Fixed a bug in `<sl-dialog>` and `<sl-drawer>` where setting `open` initially didn't set a focus trap
- Fixed a bug that resulted in form controls having incorrect validity when `disabled` was initially set [#473](https://github.com/shoelace-style/shoelace/issues/473)
- Fixed a bug in the docs that caused the metadata file to be requested twice
- Fixed a bug where tabbing out of a modal would cause the browser to lag [#466](https://github.com/shoelace-style/shoelace/issues/466)
- Updated the docs to use the new `custom-elements.json` for component metadata

## 2.0.0-beta.44

- 🚨 BREAKING: all `invalid` props on form controls now reflect validity before interaction [#455](https://github.com/shoelace-style/shoelace/issues/455)
- Allow `null` to be passed to disable animations in `setDefaultAnimation()` and `setAnimation()`
- Converted build scripts to ESM
- Fixed a bug in `<sl-checkbox>` where `invalid` did not update properly
- Fixed a bug in `<sl-dropdown>` where a `keydown` listener wasn't cleaned up properly
- Fixed a bug in `<sl-select>` where `sl-blur` was emitted prematurely [#456](https://github.com/shoelace-style/shoelace/issues/456)
- Fixed a bug in `<sl-select>` where no selection with `multiple` resulted in an incorrect value [#457](https://github.com/shoelace-style/shoelace/issues/457)
- Fixed a bug in `<sl-select>` where `sl-change` was emitted immediately after connecting to the DOM [#458](https://github.com/shoelace-style/shoelace/issues/458)
- Fixed a bug in `<sl-select>` where non-printable keys would cause the menu to open
- Fixed a bug in `<sl-select>` where `invalid` was not always updated properly
- Reworked the `@watch` decorator to use `update` instead of `updated` resulting in better performance and flexibility

## 2.0.0-beta.43

- Added `?` to optional arguments in methods tables in the docs
- Added the `scrollPosition()` method to `<sl-textarea>` to get/set scroll position
- Added initial tests for `<sl-dialog>`, `<sl-drawer>`, `<sl-dropdown>`, and `<sl-tooltip>`
- Fixed a bug in `<sl-tab-group>` where scrollable tab icons were not displaying correctly
- Fixed a bug in `<sl-dialog>` and `<sl-drawer>` where preventing clicks on the overlay no longer worked as described [#452](https://github.com/shoelace-style/shoelace/issues/452)
- Fixed a bug in `<sl-dialog>` and `<sl-drawer>` where setting initial focus no longer worked as described [#453](https://github.com/shoelace-style/shoelace/issues/453)
- Fixed a bug in `<sl-card>` where the `slotchange` listener wasn't attached correctly [#454](https://github.com/shoelace-style/shoelace/issues/454)
- Fixed lifecycle bugs in a number of components [#451](https://github.com/shoelace-style/shoelace/issues/451)
- Removed `fill: both` from internal animate utility so styles won't "stick" by default [#450](https://github.com/shoelace-style/shoelace/issues/450)

## 2.0.0-beta.42

This release addresses an issue with the `open` attribute no longer working in a number of components, as a result of the changes in beta.41. It also removes a small but controversial feature that complicated show/hide logic and led to a poor experience for developers and end users.

There are two ways to show/hide affected components: by calling `show() | hide()` and by toggling the `open` prop. Previously, it was possible to call `event.preventDefault()` in an `sl-show | sl-hide ` handler to stop the component from showing/hiding. The problem becomes obvious when you set `el.open = false`, the event gets canceled, and in the next cycle `el.open` has reverted to `true`. Not only is this unexpected, but it also doesn't play nicely with frameworks. Additionally, this made it impossible to await `show() | hide()` since there was a chance they'd never resolve.

Technical reasons aside, canceling these events seldom led to a good user experience, so the decision was made to no longer allow `sl-show | sl-hide` to be cancelable.

- 🚨 BREAKING: `sl-show` and `sl-hide` events are no longer cancelable
- Added Iconoir example to the icon docs
- Added Web Test Runner
- Added initial tests for `<sl-alert>` and `<sl-details>`
- Changed the `cancelable` default to `false` for the internal `@event` decorator
- Fixed a bug where toggling `open` stopped working in `<sl-alert>`, `<sl-dialog>`, `<sl-drawer>`, `<sl-dropdown>`, and `<sl-tooltip>`
- Fixed a bug in `<sl-range>` where setting a value outside the default `min` or `max` would clamp the value [#448](https://github.com/shoelace-style/shoelace/issues/448)
- Fixed a bug in `<sl-dropdown>` where placement wouldn't adjust properly when shown [#447](https://github.com/shoelace-style/shoelace/issues/447)
- Fixed a bug in the internal `shimKeyframesHeightAuto` utility that caused `<sl-details>` to measure heights incorrectly [#445](https://github.com/shoelace-style/shoelace/issues/445)
- Fixed a number of imports that should have been type imports
- Updated Lit to 2.0.0-rc.2
- Updated esbuild to 0.12.4

## 2.0.0-beta.41

This release changes how components animate. In previous versions, CSS transitions were used for most show/hide animations. Transitions are problematic due to the way `transitionend` works. This event fires once _per transition_, and it's impossible to know which transition to look for when users can customize any possible CSS property. Because of this, components previously required the `opacity` property to transition. If a user were to prevent `opacity` from transitioning, the component wouldn't hide properly and the `sl-after-show|hide` events would never emit.

CSS animations, on the other hand, have a more reliable `animationend` event. Alas, `@keyframes` don't cascade and can't be injected into a shadow DOM via CSS, so there would be no good way to customize them.

The most elegant solution I found was to use the [Web Animations API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Animations_API), which offers more control over animations at the expense of customizations being done in JavaScript. Fortunately, through the [Animation Registry](/getting-started/customizing#animations), you can customize animations globally and/or per component with a minimal amount of code.

- 🚨 BREAKING: changed `left` and `right` placements to `start` and `end` in `<sl-drawer>`
- 🚨 BREAKING: changed `left` and `right` placements to `start` and `end` in `<sl-tab-group>`
- 🚨 BREAKING: removed `--hide-duration`, `--hide-timing-function`, `--show-duration`, and `--show-timing-function` custom properties from `<sl-tooltip>` (use the Animation Registry instead)
- Added the Animation Registry
- Fixed a bug where removing `<sl-dropdown>` from the DOM and adding it back destroyed the popover reference [#443](https://github.com/shoelace-style/shoelace/issues/443)
- Updated animations for `<sl-alert>`, `<sl-dialog>`, `<sl-drawer>`, `<sl-dropdown>`, and `<sl-tooltip>` to use the Animation Registry instead of CSS transitions
- Improved a11y by respecting `prefers-reduced-motion` for all show/hide animations
- Improved `--show-delay` and `--hide-delay` behavior in `<sl-tooltip>` so they only apply on hover
- Removed the internal popover utility

## 2.0.0-beta.40

- 🚨 BREAKING: renamed `<sl-responsive-embed>` to `<sl-responsive-media>` and added support for images and videos [#436](https://github.com/shoelace-style/shoelace/issues/436)
- Fixed a bug where setting properties before an element was defined would render incorrectly [#425](https://github.com/shoelace-style/shoelace/issues/425)
- Fixed a bug that caused all modules to be imported when cherry picking certain components [#439](https://github.com/shoelace-style/shoelace/issues/439)
- Fixed a bug where the scrollbar would reposition `<sl-dialog>` on hide causing it to jump [#424](https://github.com/shoelace-style/shoelace/issues/424)
- Fixed a bug that prevented the project from being built in a Windows environment
- Improved a11y in `<sl-progress-ring>`
- Removed `src/utilities/index.ts` to prevent tree-shaking confusion (please import utilities directly from their respective modules)
- Removed global `[hidden]` styles so they don't affect anything outside of components
- Updated to Bootstrap Icons 1.5.0
- Updated React docs to use [`@shoelace-style/react`](https://github.com/shoelace-style/react)
- Updated NextJS docs [#434](https://github.com/shoelace-style/shoelace/pull/434)
- Updated TypeScript to 4.2.4

## 2.0.0-beta.39

- Added experimental `<sl-qr-code>` component
- Added `system` icon library and updated all components to use this instead of the default icon library [#420](https://github.com/shoelace-style/shoelace/issues/420)
- Updated to esbuild 0.8.57
- Updated to Lit 2.0.0-rc.1 and lit-html 2.0.0-rc.2

## 2.0.0-beta.38

- 🚨 BREAKING: `<sl-radio>` components must be located inside an `<sl-radio-group>` for proper accessibility [#218](https://github.com/shoelace-style/shoelace/issues/218)
- Added `<sl-radio-group>` component [#218](https://github.com/shoelace-style/shoelace/issues/218)
- Added `--header-spacing`, `--body-spacing`, and `--footer-spacing` custom properties to `<sl-drawer>` and `<sl-dialog>` [#409](https://github.com/shoelace-style/shoelace/issues/409)
- Fixed a bug where `<sl-menu-item>` prefix and suffix slots wouldn't always receive the correct spacing
- Fixed a bug where `<sl-badge>` used `--sl-color-white` instead of the correct design tokens [#407](https://github.com/shoelace-style/shoelace/issues/407)
- Fixed a bug in `<sl-dialog>` and `<sl-drawer>` where the escape key would cause parent components to close
- Fixed a race condition bug in `<sl-icon>` [#410](https://github.com/shoelace-style/shoelace/issues/410)
- Improved focus trap behavior in `<sl-dialog>` and `<sl-drawer>`
- Improved a11y in `<sl-dialog>` and `<sl-drawer>` by restoring focus to trigger on close
- Improved a11y in `<sl-radio>` with Windows high contrast mode [#215](https://github.com/shoelace-style/shoelace/issues/215)
- Improved a11y in `<sl-select>` by preventing the chevron icon from being announced
- Internal: removed the `options` argument from the modal utility as focus trapping is now handled internally

## 2.0.0-beta.37

- Added `click()` method to `<sl-checkbox>`, `<sl-radio>`, and `<sl-switch>`
- Added the `activation` attribute to `<sl-tab-group>` to allow for automatic and manual tab activation
- Added `npm run create <tag>` script to scaffold new components faster
- Fixed a bug in `<sl-tooltip>` where events weren't properly cleaned up on disconnect
- Fixed a bug in `<sl-tooltip>` where they wouldn't display after toggling `disabled` off and on again [#391](https://github.com/shoelace-style/shoelace/issues/391)
- Fixed a bug in `<sl-details>` where `show()` and `hide()` would toggle the control when disabled
- Fixed a bug in `<sl-color-picker>` where setting `value` wouldn't update the control
- Fixed a bug in `<sl-tab-group>` where tabs that are initially disabled wouldn't receive the indicator on activation [#403](https://github.com/shoelace-style/shoelace/issues/403)
- Fixed incorrect event names for `sl-after-show` and `sl-after-hide` in `<sl-details>`
- Improved a11y for disabled buttons that are rendered as links
- Improved a11y for `<sl-button-group>` by adding the correct `role` attribute
- Improved a11y for `<sl-input>`, `<sl-range>`, `<sl-select>`, and `<sl-textarea>` so labels and helper text are read properly by screen readers
- Removed `sl-show`, `sl-hide`, `sl-after-show`, `sl-after-hide` events from `<sl-color-picker>` (the color picker's visibility cannot be controlled programmatically so these shouldn't have been exposed; the dropdown events now bubble up so you can listen for those instead)
- Reworked `<sl-button-group>` so it doesn't require light DOM styles

## 2.0.0-beta.36

- 🚨 BREAKING: renamed `setFocus()` to `focus()` in button, checkbox, input, menu item, radio, range, rating, select, switch, and tab
- 🚨 BREAKING: renamed `removeFocus()` to `blur()` in button, checkbox, input, menu item, radio, range, rating, select, switch, and tab
- Added `click()` method to `<sl-button>`
- Fixed a bug where toggling `open` on `<sl-drawer>` would skip the transition
- Fixed a bug where `<sl-color-picker>` could be opened when disabled
- Fixed a bug in `<sl-color-picker>` that caused erratic slider behaviors [#388](https://github.com/shoelace-style/shoelace/issues/388) [#389](https://github.com/shoelace-style/shoelace/issues/389)
- Fixed a bug where `<sl-details>` wouldn't always render the correct height when open initially [#357](https://github.com/shoelace-style/shoelace/issues/357)
- Renamed `components.json` to `metadata.json`
- Updated to the prerelease versions of LitElement and lit-html
- Updated to Bootstrap Icons 1.4.1

## 2.0.0-beta.35

- Fixed a bug in `<sl-animation>` where `sl-cancel` and `sl-finish` events would never fire
- Fixed a bug where `<sl-alert>` wouldn't always transition properly
- Fixed a bug where using `<sl-menu>` inside a shadow root would break keyboard selections [#382](https://github.com/shoelace-style/shoelace/issues/382)
- Fixed a bug where toggling `multiple` in `<sl-select>` would lead to a stale display label
- Fixed a bug in `<sl-tab-group>` where changing `placement` could result in the active tab indicator being drawn a few pixels off
- Fixed a bug in `<sl-button>` where link buttons threw an error on focus, blur, and click
- Improved `@watch` decorator to run after update instead of during
- Updated `<sl-menu-item>` checked icon to `check` instead of `check2`
- Upgraded the status of `<sl-resize-observer>` from experimental to stable

## 2.0.0-beta.34

This release changes the way components are registered if you're [cherry picking](/getting-started/installation?id=cherry-picking) or [using a bundler](/getting-started/installation?id=bundling). This recommendation came from the LitElement team and simplifies Shoelace's dependency graph. It also eliminates the need to call a `register()` function before using each component.

From now on, importing a component will register it automatically. The caveat is that bundlers may not tree shake the library properly if you import from `@shoelace-style/shoelace`, so the recommendation is to import components and utilities from their corresponding files instead.

- 🚨 BREAKING: removed `all.shoelace.js` (use `shoelace.js` instead)
- 🚨 BREAKING: component modules now have a side effect, so bundlers may not tree shake properly when importing from `@shoelace-style/shoelace` (see the [installation page](/getting-started/installation?id=bundling) for more details and how to update)
- Added `sl-clear` event to `<sl-select>`
- Fixed a bug where dynamically changing menu items in `<sl-select>` would cause the display label to be blank [#374](https://github.com/shoelace-style/shoelace/discussions/374)
- Fixed a bug where setting the `value` attribute or property on `<sl-input>` and `<sl-textarea>` would trigger validation too soon
- Fixed the margin in `<sl-menu-label>` to align with menu items
- Fixed `autofocus` attributes in `<sl-input>` and `<sl-textarea>`
- Improved types for `autocapitalize` in `<sl-input>` and `<sl-textarea>`
- Reverted the custom `@tag` decorator in favor of `@customElement` to enable auto-registration

## 2.0.0-beta.33

- Fixed a bug where link buttons could have incorrect `target`, `download`, and `rel` props
- Fixed `aria-label` and `aria-labelledby` props in `<sl-dialog>` and `<sl-drawer>`
- Fixed `tabindex` attribute in `<sl-menu>`
- Fixed a bug in `<sl-select>` where tags would always render as pills
- Fixed a bug in `<sl-button>` where calling `setFocus()` would throw an error

## 2.0.0-beta.32

- Added tag name maps so TypeScript can identify Shoelace elements [#371](https://github.com/shoelace-style/shoelace/pull/371)
- Fixed a bug where the active tab indicator wouldn't render properly on tabs styled with `flex-end` [#355](https://github.com/shoelace-style/shoelace/issues/355)
- Fixed a bug where `sl-change` wasn't emitted by `<sl-checkbox>` or `<sl-switch>` [#370](https://github.com/shoelace-style/shoelace/issues/370)
- Fixed a bug where some props weren't being watched correctly in `<sl-alert>` and `<sl-color-picker>`
- Improved `@watch` decorator so watch handlers don't run before the first render
- Removed guards that were added due to previous watch handler behavior

## 2.0.0-beta.31

- Add touch support to `<sl-rating>` [#362](https://github.com/shoelace-style/shoelace/pull/362)
- Fixed a bug where the `open` attribute on `<sl-details>` would prevent it from opening [#357](https://github.com/shoelace-style/shoelace/issues/357)
- Fixed event detail type parsing so component class names are shown instead of `default`

## 2.0.0-beta.30

- Fix default exports for all components so cherry picking works again [#365](https://github.com/shoelace-style/shoelace/issues/365)
- Revert FOUC base style because it interferes with some framework and custom element use cases

## 2.0.0-beta.29

**This release migrates component implementations from Shoemaker to LitElement.** Due to feedback from the community, Shoelace will rely on a more heavily tested library for component implementations. This gives you a more solid foundation and reduces my maintenance burden. Thank you for all your comments, concerns, and encouragement! Aside from that, everything else from beta.28 still applies plus the following.

- 🚨 BREAKING: removed the `symbol` property from `<sl-rating>` and reverted to `getSymbol` for optimal flexibility
- Added `vscode.html-custom-data.json` to the build to support IntelliSense (see [the usage section](/getting-started/usage#code-completion) for details)
- Added a base style to prevent FOUC before components are defined
- Fixed bug where TypeScript types weren't being generated [#364](https://github.com/shoelace-style/shoelace/pull/364)
- Improved vertical padding in `<sl-tooltip>`
- Moved chunk files into a separate folder
- Reverted menu item active styles
- Updated esbuild to 0.8.54

## 2.0.0-beta.28

**This release includes a major under the hood overhaul of the library and how it's distributed.** Until now, Shoelace was developed with Stencil. This release moves to a lightweight tool called Shoemaker, a homegrown utility that provides declarative templating and data binding while reducing the boilerplate required for said features.

This change in tooling addresses a number of longstanding bugs and limitations. It also gives us more control over the library and build process while streamlining development and maintenance. Instead of two different distributions, Shoelace now offers a single, standards-compliant collection of ES modules. This may affect how you install and use the library, so please refer to the [installation page](/getting-started/installation) for details.

!> Due to the large number of internal changes, I would consider this update to be less stable than previous ones. If you're using Shoelace in a production app, consider holding off until the next beta to allow for more exhaustive testing from the community. Please report any bugs you find on the [issue tracker](https://github.com/shoelace-style/shoelace/issues).

The component API remains the same except for the changes noted below. Thanks for your patience as I work diligently to make Shoelace more stable and future-proof. 🙌

- 🚨 BREAKING: removed the custom elements bundle (you can import ES modules directly)
- 🚨 BREAKING: removed `getAnimationNames()` and `getEasingNames()` methods from `<sl-animation>` (you can import them from `utilities/animation.js` instead)
- 🚨 BREAKING: removed the `<sl-icon-library>` component since it required imperative initialization (you can import the `registerIconLibrary()` function from `utilities/icon-library.js` instead)
- 🚨 BREAKING: removed the experimental `<sl-theme>` component due to technical limitations (you should set the `sl-theme-{name}` class on the `<body>` instead)
- 🚨 BREAKING: moved the base stylesheet from `dist/shoelace.css` to `dist/themes/base.css`
- 🚨 BREAKING: moved `icons` into `assets/icons` to make future assets easier to colocate
- 🚨 BREAKING: changed `getSymbol` property in `<sl-rating>` to `symbol` (it now accepts a string or a function that returns an icon name)
- 🚨 BREAKING: renamed `setAssetPath()` to `setBasePath()` and added the ability to set the library's base path with a `data-shoelace` attribute (`setBasePath()` is exported from `utilities/base-path.js`)
- Fixed `min` and `max` types in `<sl-input>` to allow numbers and strings [#330](https://github.com/shoelace-style/shoelace/issues/330)
- Fixed a bug where `<sl-checkbox>`, `<sl-radio>`, and `<sl-switch>` controls would shrink with long labels [#325](https://github.com/shoelace-style/shoelace/issues/325)
- Fixed a bug in `<sl-select>` where the dropdown menu wouldn't reposition when the box resized [#340](https://github.com/shoelace-style/shoelace/issues/340)
- Fixed a bug where ignoring clicks and clicking the overlay would prevent the escape key from closing the dialog/drawer [#344](https://github.com/shoelace-style/shoelace/pull/344)
- Removed the lazy loading dist (importing `shoelace.js` will load and register all components now)
- Switched from Stencil to Shoemaker
- Switched to a custom build powered by [esbuild](https://esbuild.github.io/)
- Updated to Bootstrap Icons 1.4.0

## 2.0.0-beta.27

- Added `handle-icon` slot to `<sl-image-comparer>` [#311](https://github.com/shoelace-style/shoelace/issues/311)
- Added `label` and `helpText` props and slots to `<sl-range>` [#318](https://github.com/shoelace-style/shoelace/issues/318)
- Added "Integrating with NextJS" tutorial to the docs, courtesy of [crutchcorn](https://github.com/crutchcorn)
- Added `content` slot to `<sl-tooltip>` [#322](https://github.com/shoelace-style/shoelace/pull/322)
- Fixed a bug in `<sl-select>` where removing a tag would toggle the dropdown
- Fixed a bug in `<sl-input>` and `<sl-textarea>` where the input might not exist when the value watcher is called [#313](https://github.com/shoelace-style/shoelace/issues/313)
- Fixed a bug in `<sl-details>` where hidden elements would receive focus when tabbing [#323](https://github.com/shoelace-style/shoelace/issues/323)
- Fixed a bug in `<sl-icon>` where `sl-error` would only be emitted for network failures [#326](https://github.com/shoelace-style/shoelace/pull/326)
- Reduced the default line-height for `<sl-tooltip>`
- Updated `<sl-menu-item>` focus styles
- Updated `<sl-select>` so tags will wrap when `multiple` is true
- Updated to Stencil 2.4.0

## 2.0.0-beta.26

- 🚨 BREAKING: Fixed animations bloat
  - Removed ~400 baked-in Animista animations because they were causing ~200KB of bloat (they can still be used with custom keyframes)
  - Reworked animations into a separate module ([`@shoelace-style/animations`](https://github.com/shoelace-style/animations)) so it's more maintainable and animations are sync with the latest version of animate.css
  - Animation and easing names are now camelCase (e.g. `easeInOut` instead of `ease-in-out`)
- Added initial E2E tests [#169](https://github.com/shoelace-style/shoelace/pull/169)
- Added the `FocusOptions` argument to all components that have a `setFocus()` method
- Added `sl-initial-focus` event to `<sl-dialog>` and `<sl-drawer>` so focus can be customized to a specific element
- Added `close-button` part to `<sl-tab>` so the close button can be customized
- Added `scroll-button` part to `<sl-tab-group>` so the scroll buttons can be customized
- Fixed a bug where `sl-hide` would be emitted twice when closing an alert with `hide()`
- Fixed a bug in `<sl-color-picker>` where the toggle button was smaller than the preview button in Safari
- Fixed a bug in `<sl-tab-group>` where activating a nested tab group didn't work properly [#299](https://github.com/shoelace-style/shoelace/issues/299)
- Fixed a bug in `<sl-tab-group>` where removing tabs would throw an error
- Fixed a bug in `<sl-alert>`, `<sl-dialog>`, `<sl-drawer>`, `<sl-select>`, and `<sl-tag>` where the close button's base wasn't exported so it couldn't be styled
- Removed `text` type from `<sl-badge>` as it was erroneously copied and never had styles
- Updated `<sl-tab-group>` so the `active` property is reflected to its attribute
- Updated the docs to show dependencies instead of dependents which is much more useful when working with the custom elements bundle
- Updated to Bootstrap Icons 1.3.0

## 2.0.0-beta.25

- 🚨 BREAKING: Reworked color tokens
  - Theme colors are now inspired by Tailwind's professionally-designed color palette
  - Color token variations now range from 50, 100, 200, 300, 400, 500, 600, 700, 800, 900, 950
  - Color token variations were inverted, e.g. 50 is lightest and 950 is darkest
  - All component styles were adapted to use the new color tokens, but visual changes are subtle
  - The dark theme was adapted use the new color tokens
  - HSL is no longer used because it is not perceptually uniform (this may be revisited when all browsers support [LCH colors](https://lea.verou.me/2020/04/lch-colors-in-css-what-why-and-how/))
- 🚨 BREAKING: Refactored `<sl-select>` to improve accessibility [#216](https://github.com/shoelace-style/shoelace/issues/216)
  - Removed the internal `<sl-input>` because it was causing problems with a11y and virtual keyboards
  - Removed `input`, `prefix` and `suffix` parts
- 🚨 BREAKING: Removed `copy-button` part from `<sl-color-picker>` since copying is now done by clicking the preview
- Added `getFormattedValue()` method to `<sl-color-picker>` so you can retrieve the current value in any format
- Added visual separators between solid buttons in `<sl-button-group>`
- Added `help-text` attribute to `<sl-input>`, `<sl-textarea>`, and `<sl-select>`
- Fixed a bug where moving the mouse while `<sl-dropdown>` is closing would remove focus from the trigger
- Fixed a bug where `<sl-menu-item>` didn't set a default color in the dark theme
- Fixed a bug where `<sl-color-picker>` preview wouldn't update in Safari
- Fixed a bug where removing an icon's `name` or `src` wouldn't remove the previously rendered SVG [#285](https://github.com/shoelace-style/shoelace/issues/285)
- Fixed a bug where disabled link buttons didn't appear disabled
- Improved button spacings and added split button example
- Improved elevation tokens in dark theme
- Improved accessibility in `<sl-tooltip>` by allowing escape to dismiss it [#219](https://github.com/shoelace-style/shoelace/issues/219)
- Improved slot detection in `<sl-card>`, `<sl-dialog>`, and `<sl-drawer>`
- Made `@types/resize-observer-browser` a dependency so users don't have to install it manually
- Refactored internal label + help text logic into a functional component used by `<sl-input>`, `<sl-textarea>`, and `<sl-select>`
- Removed `sl-blur` and `sl-focus` events from `<sl-menu>` since menus can't have focus as of 2.0.0-beta.22
- Updated `<sl-spinner>` so the indicator is more obvious
- Updated to Bootstrap Icons 1.2.2

## 2.0.0-beta.24

- Added `<sl-format-date>` component
- Added `indeterminate` state to `<sl-progress-bar>` [#274](https://github.com/shoelace-style/shoelace/issues/274)
- Added `--track-color`, `--indicator-color`, and `--label-color` to `<sl-progress-bar>` [#276](https://github.com/shoelace-style/shoelace/issues/276)
- Added `allow-scripts` attribute to `<sl-include>` [#280](https://github.com/shoelace-style/shoelace/issues/280)
- Fixed a bug where `<sl-menu-item>` color variable was incorrect [#272](https://github.com/shoelace-style/shoelace/issues/272)
- Fixed a bug where `<sl-dialog>` and `<sl-drawer>` would emit the `sl-hide` event twice [#275](https://github.com/shoelace-style/shoelace/issues/275)
- Fixed a bug where calling `event.preventDefault()` on certain form elements wouldn't prevent `<sl-form>` from submitting [#277](https://github.com/shoelace-style/shoelace/issues/277)
- Fixed drag handle orientation in `<sl-image-comparer>`
- Restyled `<sl-spinner>` so the track is visible and the indicator is smaller.
- Removed `resize-observer-polyfill` in favor of `@types/resize-observer-browser` since all target browsers support `ResizeObserver`
- Upgraded the status of `<sl-form>`, `<sl-image-comparer>`, and `<sl-include>` from experimental to stable

## 2.0.0-beta.23

- Added `<sl-format-number>` component
- Added `<sl-relative-time>` component
- Added `closable` attribute to `<sl-tab>`
- Added experimental `<sl-resize-observer>` utility
- Added experimental `<sl-theme>` utility and updated theming documentation
- Fixed a bug where `<sl-menu-item>` wouldn't render properly in the dark theme
- Fixed a bug where `<sl-select>` would show an autocomplete menu
- Improved placeholder contrast in dark theme
- Updated to Bootstrap Icons 1.1.0
- Updated to Stencil 2.3.0

## 2.0.0-beta.22

- 🚨 BREAKING: Refactored `<sl-menu>` and `<sl-menu-item>` to improve accessibility by using proper focus states [#217](https://github.com/shoelace-style/shoelace/issues/217)
  - Moved `tabindex` from `<sl-menu>` to `<sl-menu-item>`
  - Removed the `active` attribute from `<sl-menu-item>` because synthetic focus states are bad for accessibility
  - Removed the `sl-activate` and `sl-deactivate` events from `<sl-menu-item>` (listen for `focus` and `blur` instead)
  - Updated `<sl-select>` so keyboard navigation still works
- Added `no-scroll-controls` attribute to `<sl-tab-group>` [#253](https://github.com/shoelace-style/shoelace/issues/253)
- Fixed a bug where setting `open` initially wouldn't show `<sl-dialog>` or `<sl-drawer>` [#255](https://github.com/shoelace-style/shoelace/issues/255)
- Fixed a bug where `disabled` could be set when buttons are rendered as links
- Fixed a bug where hoisted dropdowns would render in the wrong position when placed inside `<sl-dialog>` [#252](https://github.com/shoelace-style/shoelace/issues/252)
- Fixed a bug where boolean aria attributes didn't explicitly set `true|false` string values in the DOM
- Fixed a bug where `aria-describedby` was never set on tooltip targets in `<sl-tooltip>`
- Fixed a bug where setting `position` on `<sl-image-comparer>` wouldn't update the divider's position
- Fixed a bug where the check icon was announced to screen readers in `<sl-menu-item>`
- Improved `<sl-icon-button>` accessibility by encouraging proper use of `label` and hiding the internal icon from screen readers [#220](https://github.com/shoelace-style/shoelace/issues/220)
- Improved `<sl-dropdown>` accessibility by attaching `aria-haspopup` and `aria-expanded` to the slotted trigger
- Refactored position logic to remove an unnecessary state variable in `<sl-image-comparer>`
- Refactored design tokens to use `rem` instead of `px` for input height and spacing [#221](https://github.com/shoelace-style/shoelace/issues/221)
- Removed `console.log` from modal utility
- Updated to Stencil 2.2.0

## 2.0.0-beta.21

- Added `label` slot to `<sl-input>`, `<sl-select>`, and `<sl-textarea>` [#248](https://github.com/shoelace-style/shoelace/issues/248)
- Added `label` slot to `<sl-dialog>` and `<sl-drawer>`
- Added experimental `<sl-include>` component
- Added status code to the `sl-error` event in `<sl-icon>`
- Fixed a bug where initial transitions didn't show in `<sl-dialog>` and `<sl-drawer>` [#247](https://github.com/shoelace-style/shoelace/issues/247)
- Fixed a bug where indeterminate checkboxes would maintain the indeterminate state when toggled
- Fixed a bug where concurrent active modals (i.e. dialog, drawer) would try to steal focus from each other
- Improved `<sl-color-picker>` grid and slider handles [#246](https://github.com/shoelace-style/shoelace/issues/246)
- Refactored `<sl-icon>` request logic and removed unused cache map
- Reworked show/hide logic in `<sl-alert>`, `<sl-dialog>`, and `<sl-drawer>` to not use reflow hacks and the `hidden` attribute
- Reworked slot logic in `<sl-card>`, `<sl-dialog>`, and `<sl-drawer>`
- Updated to Popper 2.5.3 to address a fixed position bug in Firefox

## 2.0.0-beta.20

- 🚨 BREAKING: Transformed all Shoelace events to lowercase ([details](#why-did-event-names-change))
- Added support for dropdowns and non-icon elements to `<sl-input>`
- Added `spellcheck` attribute to `<sl-input>`
- Added `<sl-icon-library>` to allow custom icon library registration
- Added `library` attribute to `<sl-icon>` and `<sl-icon-button>`
- Added "Integrating with Rails" tutorial to the docs, courtesy of [ParamagicDev](https://github.com/ParamagicDev)
- Fixed a bug where `<sl-progress-ring>` rendered incorrectly when zoomed in Safari [#227](https://github.com/shoelace-style/shoelace/issues/227>)
- Fixed a bug where tabbing into slotted elements closes `<sl-dropdown>` when used in a shadow root [#223](https://github.com/shoelace-style/shoelace/issues/223)
- Fixed a bug where scroll anchoring caused undesirable scrolling when `<sl-details>` are grouped

### Why did event names change?

Shoelace events were updated to use a lowercase, kebab-style naming convention. Instead of event names such as `slChange` and `slAfterShow`, you'll need to use `sl-change` and `sl-after-show` now.

This change was necessary to address a critical issue in frameworks that use DOM templates with declarative event bindings such as `<sl-button @slChange="handler">`. Due to HTML's case-insensitivity, browsers translate attribute names to lowercase, turning `@slChange` into `@slchange`, making it impossible to listen to `slChange`.

While declarative event binding is a non-standard feature, not supporting it would make Shoelace much harder to use in popular frameworks. To accommodate those users and provide a better developer experience, we decided to change the naming convention while Shoelace is still in beta.

The following pages demonstrate why this change was necessary.

- [This Polymer FAQ from Custom Elements Everywhere](https://custom-elements-everywhere.com/#faq-polymer)
- [Vue's Event Names documentation](https://vuejs.org/v2/guide/components-custom-events.html#Event-Names)

## 2.0.0-beta.19

- Added `input`, `label`, `prefix`, `clear-button`, `suffix`, `help-text` exported parts to `<sl-select>` to make the input customizable
- Added toast notifications through the `toast()` method on `<sl-alert>`
- Fixed a bug where mouse events would bubble up when `<sl-button>` was disabled, causing tooltips to erroneously appear
- Fixed a bug where pressing space would open and immediately close `<sl-dropdown>` panels in Firefox
- Fixed a bug where `<sl-tooltip>` would throw an error on init
- Fixed a bug in custom keyframes animation example
- Refactored clear logic in `<sl-input>`

## 2.0.0-beta.18

- Added `name` and `invalid` attribute to `<sl-color-picker>`
- Added support for form submission and validation to `<sl-color-picker>`
- Added touch support to demo resizers in the docs
- Added `<sl-responsive-embed>` component
- Fixed a bug where swapping an animated element wouldn't restart the animation in `<sl-animation>`
- Fixed a bug where the cursor was incorrect when `<sl-select>` was disabled
- Fixed a bug where `slblur` and `slfocus` were emitted twice in `<sl-select>`
- Fixed a bug where clicking on `<sl-menu>` wouldn't focus it
- Fixed a bug in the popover utility where `onAfterShow` would fire too soon
- Fixed a bug where `bottom` and `right` placements didn't render properly in `<sl-tab-group>`
- Improved keyboard logic in `<sl-dropdown>`, `<sl-menu>`, and `<sl-select>`
- Updated `<sl-animation>` to stable
- Updated to Stencil 2.0 (you may need to purge `node_modules` and run `npm install` after pulling)
- Updated entry points in `package.json` to reflect new filenames generated by Stencil 2

## 2.0.0-beta.17

- Added `minlength` and `spellcheck` attributes to `<sl-textarea>`
- Fixed a bug where clicking a tag in `<sl-select>` wouldn't toggle the menu
- Fixed a bug where options where `<sl-select>` options weren't always visible or scrollable
- Fixed a bug where setting `null` on `<sl-input>`, `<sl-textarea>`, or `<sl-select>` would throw an error
- Fixed a bug where `role` was on the wrong element and aria attribute weren't explicit in `<sl-checkbox>`, `<sl-switch>`, and `<sl-radio>`
- Fixed a bug where dynamically adding/removing a slot wouldn't work as expected in `<sl-card>`, `<sl-dialog>`, and `<sl-drawer>`
- Fixed a bug where the value wasn't updated and events weren't emitted when using `setRangeText` in `<sl-input>` and `<sl-textarea>`
- Optimized `hasSlot` utility by using a simpler selector
- Updated Bootstrap Icons to 1.0.0 with many icons redrawn and improved
- Updated contribution guidelines

**Form validation has been reworked and is much more powerful now!**

- The `invalid` attribute now reflects the control's validity as determined by the browser's constraint validation API
- Added `required` to `<sl-checkbox>`, `<sl-select>`, and `<sl-switch>`
- Added `reportValidity()` and `setCustomValidity()` methods to all form controls
- Added validation checking for custom and native form controls to `<sl-form>`
- Added `novalidate` attribute to `<sl-form>` to disable validation
- Removed the `valid` attribute from all form controls
- Removed valid and invalid design tokens and related styles (you can use your own custom styles to achieve this)

## 2.0.0-beta.16

- Added `hoist` attribute to `<sl-color-picker>`, `<sl-dropdown>`, and `<sl-select>` to work around panel clipping
- Added `<sl-format-bytes>` utility component
- Added `clearable` and `required` props to `<sl-select>`
- Added `slclear` event to `<sl-input>`
- Added keyboard support to the preview resizer in the docs
- Fixed a bug where the `aria-selected` state was incorrect in `<sl-menu-item>`
- Fixed a bug where custom properties applied to `<sl-tooltip>` didn't affect show/hide transitions
- Fixed a bug where `--sl-input-color-*` custom properties had no effect on `<sl-input>` and `<sl-textarea>`
- Refactored `<sl-dropdown>` and `<sl-tooltip>` to use positioner elements so panels/tooltips can be customized easier

## 2.0.0-beta.15

- Added `image-comparer` component
- Added `--width`, `--height`, and `--thumb-size` custom props to `<sl-switch>`
- Fixed an `aria-labelledby` attribute typo in a number of components
- Fixed a bug where the `change` event wasn't updating the value in `<sl-input>`
- Fixed a bug where `<sl-color-picker>` had the wrong border color in the dark theme
- Fixed a bug where `<sl-menu-item>` had the wrong color in dark mode when disabled
- Fixed a bug where WebKit's autocomplete styles made inputs looks broken
- Fixed a bug where aria labels were wrong in `<sl-select>`
- Fixed a bug where clicking the label wouldn't focus the control in `<sl-select>`

## 2.0.0-beta.14

- Added dark theme
- Added `--sl-panel-background-color` and `--sl-panel-border-color` tokens
- Added `--tabs-border-color` custom property to `<sl-tab-group>`
- Added `--track-color` custom property to `<sl-range>`
- Added `tag` part to `<sl-select>`
- Updated `package.json` so custom elements imports can be consumed from the root
- Fixed a bug where scrolling dialogs didn't resize properly in Safari
- Fixed a bug where `slshow` and `slhide` would be emitted twice in some components
- Fixed a bug where `custom-elements/index.d.ts` was broken due to an unclosed comment (fixed in Stencil 1.17.3)
- Fixed bug where inputs were not using border radius tokens
- Fixed a bug where the text color was being erroneously set in `<sl-progress-ring>`
- Fixed a bug where `<sl-progress-bar>` used the wrong part name internally for `indicator`
- Removed background color from `<sl-menu>`
- Updated to Stencil 1.17.3

## 2.0.0-beta.13

- Added `slactivate` and `sldeactivate` events to `<sl-menu-item>`
- Added experimental `<sl-animation>` component
- Added shields to documentation
- Fixed a bug where link buttons would have `type="button"`
- Fixed a bug where button groups with tooltips experienced an odd spacing issue in Safari
- Fixed a bug where scrolling in dropdowns/selects didn't work properly on Windows (special thanks to [Trendy](http://github.com/trendy) for helping troubleshoot!)
- Fixed a bug where selecting a menu item in a dropdown would cause Safari to scroll
- Fixed a bug where type to select wouldn't accept symbols
- Moved scrolling logic from `<sl-menu>` to `<sl-dropdown>`

## 2.0.0-beta.12

- Added support for `href`, `target`, and `download` to buttons
- Fixed a bug where buttons would have horizontal spacing in Safari
- Fixed a bug that caused an import resolution error when using Shoelace in a Stencil app

## 2.0.0-beta.11

- Added button group component
- Fixed icon button alignment
- Fixed a bug where focus visible observer wasn't removed from `<sl-details>`
- Replaced the deprecated `componentDidUnload` lifecycle method with `disconnectedCallback` to prevent issues with frameworks

## 2.0.0-beta.10

- Added community page to the docs
- Fixed a bug where many components would erroneously receive an `id` when using the custom elements bundle
- Fixed a bug where tab groups weren't scrollable with the mouse

## 2.0.0-beta.9

- Added the icon button component
- Added the skeleton component
- Added the `typeToSelect` method to menu so type-to-select behavior can be controlled externally
- Added the `pulse` attribute to badge
- Fixed a bug where hovering over select showed the wrong cursor
- Fixed a bug where tabbing into a select control would highlight the label
- Fixed a bug where tabbing out of a select control wouldn't close it
- Fixed a bug where closing dropdowns wouldn't give focus back to the trigger
- Fixed a bug where type-to-select wasn't working after the first letter
- Fixed a bug where clicking on menu items and dividers would steal focus from the menu
- Fixed a bug where the color picker wouldn't parse uppercase values
- Removed the `no-footer` attribute from dialog and drawer (slot detection is automatic, so the attribute is not required)
- Removed `close-icon` slot from alert
- Replaced make-shift icon buttons with `<sl-icon-button>` in alert, dialog, drawer, and tag
- Updated Stencil to 1.17.1
- Switched to jsDelivr for better CDN performance

## 2.0.0-beta.8

- Added the card component
- Added `--focus-ring` custom property to tab
- Fixed a bug where range tooltips didn't appear on iOS
- Fixed constructor bindings so they don't break the custom elements bundle
- Fixed tag color contrast to be AA compliant
- Fixed a bug that made it difficult to vertically align rating
- Fixed a bug where dropdowns would always close on mousedown when inside a shadow root
- Made tag text colors AA compliant
- Promoted badge to stable
- Refactored `:host` variables and moved non-display props to base elements
- Refactored event handler bindings to occur in `connectedCallback` instead of the constructor
- Refactored scroll locking logic to use `Set` instead of an array
- Updated the custom elements bundle documentation and added bundler examples
- Upgraded Stencil to 1.17.0-0 (next) to fix custom elements bundle

## 2.0.0-beta.7

- Added links to version 1 resources to the docs
- Added rating component
- Fixed a bug where some build files were missing
- Fixed clearable tags demo
- Fixed touch icon size in docs

## 2.0.0-beta.6

- Enabled the `dist-custom-elements-bundle` output target
- Fixed a bug where nested form controls were ignored in `<sl-form>`

## 2.0.0-beta.5

- Fixed bug where `npm install` would fail due to postinstall script
- Removed unused dependency

## 2.0.0-beta.4

- Added `pill` variation to badges
- Fixed a bug where all badges had `pointer-events: none`
- Fixed `@since` props to show 2.0 instead of 1.0
- Fixed giant cursors in inputs in Safari
- Fixed color picker input width in Safari
- Fixed initial transitions for drawer, dialog, and popover consumers
- Fixed a bug where dialog, dropdown, and drawer would sometimes not transition in on the first open
- Fixed various documentation typos

## 2.0.0-beta.3

- Fix version in docs
- Remove custom elements bundle

## 2.0.0-beta.2

- Fix quick start and installation URLs
- Switch Docsify theme
- Update line heights tokens

## 2.0.0-beta.1

- Initial release
