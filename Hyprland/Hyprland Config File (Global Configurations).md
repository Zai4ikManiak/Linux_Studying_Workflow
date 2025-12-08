Gloabla configurations for Hyprland can be split into several parts:

### General Configurations

<details>

<summary><strong>General</strong></summary>

</br>

```c++
# Example of configuration file:

general {

	# Configuring Default Windows behavior.
	border_size = 3
	
	gaps_in = 5
	gaps_out = 20
	
	col.active_border = rgb(9c1010)
	col.inactive_border = rgb(545353)

	resize_on_border = false
	extend_on_border = 5
	hover_icon_on_border = false

	modal_parent_blocking = true

	# Configure Grouped Windows
	col.nogroup_border_active = 0xd10202ff
	col.nogroup_border = 0xe6e6e6ff

	# Gaps between workspaces
	gaps_workspaces = 0

	# Allow Tearing page
	allow_tearing = false

	# Specify layout
	layout = dwindle

	# Windows focus fall-back
	no_focus_fallback = false

	# Configuring Default Floating default
	no_border_on_floating = true
	float_gaps = 10
	resize_corner = 1
	snap {
		enabled = true
		window_gap = 10
		monitor_gap = 10
		border_overlap = false
		respect_gaps = false
	}
}

```

</br>

<details>

<summary>Windows Configurations</summary>

</br>

| Name | Category | Description | Type |
| :--- | :--- | :--- | :--- |
| `border_size` | Window | Size of the border around windows. | **int** |
| `gaps_in`</br> |  Window | Gaps between windows.</br>It support css style gaps (top, right, buttom, left). | **int** |
| `gaps_out`</br> | Window |Gaps between windows and monitor edges.</br>It support css style gaps (top, right, buttom, left). | **int** |
| `col.inactive_border` | Window | Border color for inactive windows. | **gradient** |
| `col.active_border` | Window | Border color for the active window. | **gradient** |
| `resize_on_border` | Window | Enables resizing windows by clicking and dragging on borders and gaps. | **bool** |
| `extend_border_grab_area`</br> | Window | Extends the area around the border where you can click and drag on.</br>Only used when `resize_on_border` is on. | **int** |
| `hover_icon_on_border` | Window | Show a cursor icon when hovering over borders.</br>Only used when `resize_on_border` is on. | **bool** |
| `modal_parent_blocking` | Window | Whether parent windows of modals will be interactive. | **bool** |
| --- | --- | --- | --- |
| `col.nogroup_border`</br> | Grouped Window</br> | Inactive border color for window that cannot be added to a group.</br>Check `denywindowfromgroup`. | **gradient** |
| `col.nogroup_border_active` | Group Window | Active border color for window that cannot be added to a group | **gradient** |
| --- | --- | --- | --- |
| `no_border_on_floating` | Floating Window | Disable borders for floating windows. | **bool** |
| `float_gaps`</br> | Floating Window | Gaps between windows and monitor edges for floating windows.</br>It support css style gaps (top, right, buttom, left). | **int** |
| `resize_corner`</br> | Floating Window</br> | Force floating windows to use a specific corner when being resized</br>1-4 going clockwise from top left, 0 to disable. | **int** |

---
</details>
<details>

</br>

<summary>Workspace Configuration</summary>

| Name | Description | Type |
| :--- | :--- | :--- |
| `gaps_workspace` | Gaps between workspaces. Stacks with `gaps_out`. | **int** |

---

</details>
<details>

<summary>Layout</summary>

</br>

| Name | Description | Type |
| :--- | :--- | :--- |
| `layout` | Which layout to use. (*dwindle/master*) | **str** |

---

</details>
<details>

<summary>Focus</summary>

</br>

| Name | Description | Type |
| :--- | :--- | :--- |
| `no_focus_fallback` | If true, will not fall back to the next available window when moving focus in a direction where no window was found. | **bool** |

---

</details>
<details>

<summary>Tearing</summary>

</br>

| Name | Description | Type |
| :--- | :--- | :--- |
| `allow_tearing` | Master switch for allowing tearing to occur. | **bool** |

</details>

---

<details>

<summary><strong>snap</strong> <ins>subfunction</ins></summary>

</br>

> **NOTE**
> 
> Used only for floating windows.

| Name | Description | Type |
| :--- | :--- | :--- |
| `enabled` | Enable snapping for floating windows. | **bool** |
| `window_gap` | Minimum gap in pixels between windows before snapping. | **int** |
| `monitor_gap` | Minimum gap in pixels between window and monitor edges before snapping. | **int** |
| `border_overlap` | If true, windows snap such that only one border’s worth of space is between them. | **bool** |
| `respect_gaps` | If true, snapping will respect gaps between windows(set in general:`gaps_in`) | **bool** |


</details>

</details>

---

<details>

<summary><strong>Decoration</strong></summary>

</br>

```c++
# Example of default decoration options.

decoration {

	rounding = 0
	rounding_power = 2.0
	
	active_opacity = 1.0
	inactive_opacity = 1.0
	fullscreen_opacity = 1.0

	dim_modal = true
	dim_special = 0.2
	dim_around = 0.4
	dim_inactive = false
	# dim_strength = 0.5

	# screen_shader = ""
	border_part_of_window = true

	blur {

	}

}
```

| Name | Description | Type |
| :--- | :--- | :--- |
| `rounding` | Rounded corners’ radius (in layout px). | **int** |
| `rounding_power`</br> | Adjust the curve used for rounding corners.</br>Larger is smoother, 2.0 is a circle, 4.0 is a squircle, 1.0 is a triangular corner. [1.0 - 10.0] | **float** |
| `active_opacity` | Opacity of active windows. [0.0 - 1.0] | **float** |
| `inactive_opacity` | Opacity of inactive windows. [0.0 - 1.0] | **float** |
| `fullscreen_opacity` | Opacity of fullscreen windows. [0.0 - 1.0] | **float** |
| `dim_modal` | Enables dimming of parents of modal windows. | **bool** |
| `dim_inactive` | Enables dimming of inactive windows. | **bool** |
| `dim_strength` | How much inactive windows should be dimmed. [0.0 - 1.0] | **float** |
| `dim_special` | How much to dim the rest of the screen by when a special workspace is open. [0.0 - 1.0] | **float** |
| `dim_around` | How much the `dimaround` window rule should dim by. [0.0 - 1.0] | **float** |
| `screen_shader`</br> | A path to a custom shader to be applied at the end of rendering.</br>Check `examples/screenShader.frag` for an example. | **str** |
| `border_part_of_window` | Whether the window border should be a part of the window. | **bool** |

---

<details>

<summary><strong>blur</strong> <ins>subfunction</ins></summary>

</details>

</details>

---
