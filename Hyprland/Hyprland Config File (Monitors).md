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
# Default parameters
monitor = <name_of_the_screen>, <resolution>, <position>, <scale>

# Extended parameters
```

### Monitorv2 Format:

```text
monitorv2 {

	output = <name_of_the_screen>
	mode = <resolution>
	position = <position>
	scale = <scale>
}
```

### Syntax Explanatation:

<details>

<summary><strong>Name of the Screen</strong></summary>

| Value | Description |
| :--- | :--- |
| `Blank Field` | Leaving the name empty will define a fallback rule to use when no other rules match. |
| `Name of the Monitor` | Rule to use on a specific monitor by it's name |

</details>
