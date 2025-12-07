Gloabla configurations for Hyprland can be split into several parts:

### General Configurations

<details>

<summary><strong>general</strong></summary>

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
| --- | --- | --- | --- |
| `col.nogroup_border`</br> | Grouped Window | Inactive border color for window that cannot be added to a group.</br>Check `denywindowfromgroup`. | **gradient** |
| `col.nogroup_border_active` | Group Window | Active border color for window that cannot be added to a group | **gradient** |
| --- | --- | --- | --- |
| `no_border_on_floating` | Floating Window | Disable borders for floating windows. | **bool** |
| `float_gaps`</br> | Floating Window | Gaps between windows and monitor edges for floating windows.</br>It support css style gaps (top, right, buttom, left). | **int** |

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

</details>


---

</details>
