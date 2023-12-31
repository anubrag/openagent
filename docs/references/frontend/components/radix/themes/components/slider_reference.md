##  Reference for nextpy/frontend/components/radix/themes/components/slider(Generated by a LLM. Pending Review)

# Slider Component

## Overview

The `Slider` component is an interactive element that allows users to select a value from a specified range by moving a thumb control along a track. It is commonly used for settings that reflect intensity levels, such as volume, brightness, or color saturation.

## Anatomy

A typical `Slider` consists of a track, a thumb control that the user can drag, and optional labels to indicate the value range.

### Basic Implementation

```python
from nextpy.components.radix.themes.components.slider import Slider

slider = Slider.create(min=0, max=100, step=1, default_value=50)
```

### Advanced Implementation

```python
from nextpy.components.radix.themes.components.slider import Slider

slider = Slider.create(
    min=0,
    max=100,
    step=1,
    value=Var(50),
    on_value_change=handle_value_change,
    orientation="horizontal",
    size="2",
    color_scheme="blue"
)

def handle_value_change(new_value):
    print(f"Slider value changed to: {new_value}")
```

## Components

The `Slider` component has the following properties:

### Properties Table

| Prop Name          | Type                              | Description                                       |
|--------------------|-----------------------------------|---------------------------------------------------|
| color              | `Var[str]`, `str`                 | Sets the slider's color.                          |
| color_scheme       | `Var[Literal]`, `Literal`         | Maps to the Radix color property.                 |
| size               | `Var[Literal["1", "2", "3"]]`, `Literal["1", "2", "3"]` | Defines the slider's size.   |
| variant            | `Var[Literal]`, `Literal`         | Chooses the variant of the slider.                |
| high_contrast      | `Var[bool]`, `bool`               | Renders the slider with higher contrast.          |
| radius             | `Var[Literal]`, `Literal`         | Overrides the theme radius.                       |
| default_value      | `Var[List[float]]`, `List[float]` | Sets the initial value of the slider.             |
| value              | `Var[float]`, `float`             | Controls the value of the slider.                 |
| min                | `Var[float]`, `float`             | Sets the minimum value of the slider.             |
| max                | `Var[float]`, `float`             | Sets the maximum value of the slider.             |
| step               | `Var[float]`, `float`             | Sets the step value of the slider.                |
| disabled           | `Var[bool]`, `bool`               | Indicates if the slider is disabled.              |
| orientation        | `Var[Literal]`, `Literal`         | Sets the orientation of the slider.               |

### Event Triggers

- `on_blur`: Triggers when the slider loses focus.
- `on_focus`: Triggers when the slider gains focus.
- `on_value_change`: Triggers when the slider value changes.
- `on_value_commit`: Triggers when the user stops dragging the slider, committing the value.

## Notes

- The `value` property should be used in conjunction with `on_value_change` to create a controlled component.
- If you want the slider to maintain its own state, use `default_value` instead of `value`.

## Best Practices

- When providing a `step` value, ensure it is appropriate for the range of values; too small a step can make the slider cumbersome to use.
- Utilize `min` and `max` props to set the slider's range to reflect the context of what it controls.
- Consider using `high_contrast` for better visibility in environments with varying contrast requirements.
- Always provide visual feedback or labels to help users understand the value they are selecting with the slider.