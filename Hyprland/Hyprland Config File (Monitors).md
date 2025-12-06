> [!NOTE]
> A Cheat Sheet for cofiguration of Monitors' parameters:

To find information related to the monitors use the below command:
```bash
hyprctl monitors all
```

---
## Syntax and Parameters

### Default Format:

```text
# ! Default parameters:

monitor = <name_of_the_screen>, <resolution>, <position>, <scale>

# ! Disable monitor

monitor = <name_of_the_screen>, disable

# ! Extended parameters added to the default parameters

# Custom Reserved Area
, <costom_reserved_area_top>, <costom_reserved_area_bottom>, <costom_reserved_area_left>, <costom_reserved_area_right>

# 10-bit Support
, bitdepth, 10

# Color Management presets
, cm, <color_management_preset>

# Rotation
, transform, <rotation_value>
```

### Monitorv2 Format:

```text
monitorv2 {

	# ! Default parameters:
	
	output = <name_of_the_screen>
	mode = <resolution>
	position = <position>
	scale = <scale>
	
	# ! Disable monitor
	disable = true

	# Extended parameters
	
	addreserved = <costom_reserved_area_top>, <costom_reserved_area_bottom>, <costom_reserved_area_left>, <costom_reserved_area_right>
	bitdepth = 10
	cm = <color_management_preset>
	transform = <rotation_value>
}
```
---
## Syntax Explanatation:

<details>

<summary><strong>Name of the Screen</strong></summary>
</br>

| Value | Description |
| :--- | :--- |
| `<Blank Field>` | Leaving the name empty will define a fallback rule to use when no other rules match. |
| `<Port Name>` | Rule to use on a specific monitor defined by it's port name. |
| `desc:<Name of the Monitor>` | Rule to use on a specific monitor by it's description from `hyprctl monitors all` |
---
</details>
<details>

<summary><strong>Screen Resolution</strong></summary>
</br>

| Value | Description |
| :--- | :--- |
| `<Fixed Parameters>` | Force 1920x1080 display, at 144Hz resolution. |
| `preferred` | Use the display’s preferred size and refresh rate. |
| `highres` | Use the highest supported resolution. |
| `highrr` | Use the highest supported refresh rate. |
| `maxwidth` | Use the widest supported resolution. |
---
</details>
<details>

<summary><strong>Position</strong></summary>
</br>

| Value | Description |
| :--- | :--- |
| `<Fixed Position>` | Force monitor layout to start at fixed position (ex. 0x0). |
| `auto` | Hyprland decide on a position. By default, it places each new monitor to the right of existing ones, using the monitor’s top left corner as the root point. |
| `auto-right/left/up/down` | Place the monitor to the right/left, above or below other monitors, also based on each monitor’s top left corner as the root. |
| `auto-center-right/left/up/down` | Place the monitor to the right/left, above or below other monitors, but calculate placement from each monitor’s center rather than its top left corner. |

> **NOTE**
>
> While specifying a monitor direction for your first monitor is allowed, this does nothing and it will be positioned at (0,0). 
> Also, the direction is always from the center out, so you can specify auto-up then auto-left, but the left monitors will just be left of the origin and above the origin. 
>
> You can also specify duplicate directions and monitors will continue to go in that direction.
---
</details>
<details>

<summary><strong>Screen Scale</strong></summary>
</br>

| Value | Description |
| :--- | :--- |
| `<Fixed value>` | A floating number, which is scaled in % (ex. 1 = 100%, 1.25 = 125%) |

---
</details>
<details>

<summary><strong>Custom Reserved Area</strong></summary>
</br>

A reserved area is an area that remains unoccupied by tiled windows. If your workflow requires a custom reserved area.

</br>

| Value | Description |
| :--- | :--- |
| `<Fixed Values>` | Integers, i.e the number in pixels of the reserved area to add. | 

> **NOTE**
>
> This does stack on top of the calculated reserved area (e.g. bars), but you may only use one of these rules per monitor in the config.
---
</details>
<details>

<summary><strong>Color Management Presets</strong></summary>
</br>

| Value | Description |
| :--- | :--- |
| `auto` | srgb for 8bpc, wide for 10bpc if supported (recommended). |
| `srgb` | sRGB primaries (default). |
| `dcip3` | DCI P3 primaries. |
| `dp3` | Apple P3 primaries. |
| `adobe` | Adobe RGB primaries. |
| `wide` | Wide color gamut, BT2020 primaries. |
| `edid` | Primaries from edid (known to be inaccurate). |
| `hdr` | Wide color gamut and HDR PQ transfer function (experimental). |
| `hdredid` | Same as hdr with edid primaries (experimental). |

---
</details>
<details>

<summary><strong>Screen Rotation</strong></summary>
</br>

| Value | Description |
| :--- | :--- |
| `0` | normal (no transforms) |
| `1` | 90 degrees |
| `2` | 180 degrees |
| `3` | 270 degrees |
| `4` | flipped |
| `5` | flipped + 90 degrees |
| `6` | flipped + 180 degrees |
| `7` | flipped + 270 degrees |
---
</details>

