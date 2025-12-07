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
| --- | --- | --- | --- |
| `col.nogroup_border`</br> | Grouped Window | Inactive border color for window that cannot be added to a group.</br>Check `denywindowfromgroup`. | **gradient** |
---
</details>
<details>

<summary>Grouped Windows</summary>

</br>

</details>
<details>

<summary>Floating Windows Configuration</summary>

</br>

| Name | Description | Type |
| :--- | :--- | :--- |
| `no_border_on_floating` | Disable borders for floating windows. | **bool** |
| `float_gaps`</br> | Gaps between windows and monitor edges for floating windows.</br>It support css style gaps (top, right, buttom, left). | **int** |

---
</details>
<details>

</br>

<summary>Workspace Configuration</summary>

| Name | Description | Type |
| :--- | :--- | :--- |
| `gaps_workspace` | Gaps between workspaces. Stacks with `gaps_out`. | **int** |

</details>

---

</details>
