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

		# Blur default configuration
		enabled = true
		size = 8
		passes = 1
		ignore_opacity = true
		new_optimization = true
		xray = false
		noise = 0.0117
		contrast = 0.8916
		brightness = 0.8172
		vibrancy = 0.1696
		vibrancy darkness = 0
		special = false
		popups = false
		popups_ignorealpha = 0.2
		input_methods = false
		input_methods_ignorealpha = 0.2
	}

	shadow {

		# Default shadow configuration

		enabled = true
		range = 4
		render_power = 3
		sharp = false
		ignore_window = true
		color = 0xee1a1a1a
		color_incative = unset
		offset = 0 0
		scale = 1.0

	}

}
```

</br>

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

</br>

| Name | Description | Type |
| :--- | :--- | :--- |
| `enabled` | Enable kawase window background blur. | **bool** |
| `size` | Blur size (distance). | **int** |
| `passes` | The amount of passes to perform. | **int** |
| `ignore_opacity` | Make the blur layer ignore the opacity of the window. | **bool** |
| `new_optimizations`</br> | Whether to enable further optimizations to the blur.</br> Recommended to leave on, as it will massively improve performance. | **bool** |
| `xray`</br> | If enabled, floating windows will ignore tiled windows in their blur.</br>Only available if `new_optimizations` is true. Will reduce overhead on floating blur significantly. | **bool** |
| `noise` | How much noise to apply. [0.0 - 1.0] | **float** |
| `contrast` | Contrast modulation for blur. [0.0 - 2.0] | **float** |
| `brightness` | Brightness modulation for blur. [0.0 - 2.0] | **float** |
| `vibrancy` | Increase saturation of blurred colors. [0.0 - 1.0] | **float** |
| `vibrancy_darkness` | How strong the effect of `vibrancy` is on dark areas . [0.0 - 1.0] | **float** |
| `special` | Whether to blur behind the special workspace. (note: expensive) | **bool** |
| `popups` | Whether to blur popups (e.g. right-click menus). | **bool** |
| `popups_ignorealpha`</br> | Works like ignorealpha in layer rules.</br>If pixel opacity is below set value, will not blur. [0.0 - 1.0] | **float** |
| `input_methods` | Whether to blur input methods (e.g. fcitx5) | **bool** |
| `input_methods_ignorealpha`</br> | Works like ignorealpha in layer rules.</br>If pixel opacity is below set value, will not blur. [0.0 - 1.0] | **float** |

---

</details>

<details>

<summary><strong>shadow</strong> <ins>subfunction</ins></summary>

</br>

| Name | Description | Type |
| :--- | :--- | :--- |
| `enabled` | Enable drop shadows on windows. | **bool** |
| `range` | Shadow range (“size”) in layout px. | **int** |
| `render_power` | In what power to render the falloff (more power, the faster the falloff) [1 - 4] | **int** |
| `sharp` | If enabled, will make the shadows sharp, akin to an infinite render power. | **bool** |
| `ignore_window` | If true, the shadow will not be rendered behind the window itself, only around it. | **bool** |
| `color` | Shadow’s color. Alpha dictates shadow’s opacity. | **color** |
| `color_inactive` | Inactive shadow color. (if not set, will fall back to color) | **color** |
| `offset` | Shadow’s rendering offset. | **vec2** |
| `scale` | Shadow’s scale. [0.0 - 1.0] | **float** |

</details>

</details>

---

<details>

<summary><strong>Animations</strong></summary>

</br>

```c++
# Example of default animation configuration

animations {

	# Enable animatinos for windows and workspaces.
	enabled = true
	workspace_wraparound = true

	# Default curves.
	#	 	 Name,				X0,		Y0,		X1,		Y1	
	besier = easeOutQuint,		0.23,	1,		0.32,	1
	besier = easeInOutCubic,	0.65,	0.55,	0.36,	1

}

```

</br>

| Name | Description | Type |
| :--- | :--- | :--- |
| `enabled` | Enable animations. | **bool** |
| `workspace_wraparound` | Enable workspace wraparound, causing directional workspace animations to animate as if the first and last workspaces were adjacent | **bool** |

</br>

> **NOTE**
> 
> `animation` = NAME, ONOFF, SPEED, CURVE [,STYLE]
> 
> - `ONOFF` use `0` to disable (if it is set, ignore further arguments) and `1` to enable.
> - `SPEED` is the amount of ds (1ds = 100ms) the animation will take.
> - `CURVE` is the bezier curve name.
> - `STYLE` (optional) is the animation style.
> 
> ---
> 
> <ins>The animations are a tree</ins>. If an animation is unset, it will inherit its parent’s values.

</br>

<details>

<summary>Animation Tree</summary>

</br>

! gloabal</br>
|</br>
\* --- > \* <ins>`windows`</ins> - styles : <ins>slide</ins>, <ins>popin</ins>, <ins>gnomed</ins></br>
|&emsp;&emsp;&emsp;|</br>
|&emsp;&emsp;&emsp;\* `windowsIn` - window open</br>
|&emsp;&emsp;&emsp;\* `windowsOut` - window close</br>
|&emsp;&emsp;&emsp;\* `windowsMove` - everything in between, moving, dragging, resizing.</br>
|</br>
\* --- > \* `layout`- styles : <ins>slide</ins>, <ins>popin</ins>, <ins>fade</ins></br>
|&emsp;&emsp;&emsp;|</br>
|&emsp;&emsp;&emsp;\* `layersIn` - layer open</br>
|&emsp;&emsp;&emsp;\*`layersOut` - layer close</br>
|</br>
\* --- > \* `fade`</br>
|&emsp;&emsp;&emsp;|</br>
|&emsp;&emsp;&emsp;\* `fadeIn` - fade in for window open</br>
|&emsp;&emsp;&emsp;\* `fadeOut` - fade out for window close</br>
|&emsp;&emsp;&emsp;\* `fadeSwitch` - fade on changing activewindow and its opacity</br>
|&emsp;&emsp;&emsp;\* `fadeShadow` - fade on changing activewindow for shadows</br>
|&emsp;&emsp;&emsp;\* `fadeDim` - the easing of the dimming of inactive windows</br>
|&emsp;&emsp;&emsp;\* `fadeLayers` - for controlling fade on layers</br>
|&emsp;&emsp;&emsp;|&emsp;&emsp;&emsp;&emsp;&emsp;|

</details>

</details>
