
# FlexLinearLayout

[![pub package](https://img.shields.io/pub/v/flex_linear_layout.svg)](https://pub.dev/packages/flex_linear_layout)  
[![likes](https://badges.bar/pub-likes/flex_linear_layout)](https://pub.dev/packages/flex_linear_layout/score)  
[![points](https://badges.bar/pub-points/flex_linear_layout)](https://pub.dev/packages/flex_linear_layout/score)

**FlexLinearLayout** dynamically switches between `Row` and `Column` based on screen orientation, with optional reversal of child order.

---

## How It Works

Depending on the `layoutPreference` and the current screen dimensions:

- If `LayoutPreference.Row` is selected:
  - Portrait: uses `Row`
  - Landscape: uses `Column`
- If `LayoutPreference.Column` is selected:
  - Portrait: uses `Column`
  - Landscape: uses `Row`

---

## 🎛️ Parameters

| Parameter              | Type                    | Default                   | Description                                      |
|------------------------|-------------------------|---------------------------|--------------------------------------------------|
| `children`             | `List<Widget>`          | —                         | Required list of widgets                        |
| `layoutPreference`     | `LayoutPreference`      | `LayoutPreference.row`    | Which layout to prefer in portrait mode         |
| `reverseDirection`     | `ReverseDirection`      | `ReverseDirection.none`   | Whether to reverse child order                  |
| `spacing`              | `double`                | `0.0`                     | Space between children                          |
| `mainAxisAlignment`    | `MainAxisAlignment`     | `MainAxisAlignment.start` | Horizontal/vertical alignment                   |
| `crossAxisAlignment`   | `CrossAxisAlignment`    | `CrossAxisAlignment.center` | Cross alignment                                |
| `mainAxisSize`         | `MainAxisSize`          | `MainAxisSize.max`        | Main axis size                                  |
| `textDirection`        | `TextDirection?`        | `null`                    | Row layout text direction                       |
| `verticalDirection`    | `VerticalDirection`     | `VerticalDirection.down`  | Column layout direction                         |
| `textBaseline`         | `TextBaseline?`         | `null`                    | Text baseline (for alignment if needed)         |

---

## 📚 Enums

### LayoutPreference

```dart
enum LayoutPreference {
  row,    // Portrait = Row, Landscape = Column
  column  // Portrait = Column, Landscape = Row
}
```

### ReverseDirection

```dart
enum ReverseDirection {
  row,      // Reverse in Row mode
  column,   // Reverse in Column mode
  none      // Do not reverse
}
```

---

## 📦 Installation

Add this to your `pubspec.yaml`:

```yaml
dependencies:
  flex_linear_layout: ^0.0.1
```

Then run:

```bash
flutter pub get
```

---


## Let’s Understand With Actual Example

**Desired UI**

### 1. Portrait Layout
> On Portrait Screen the first child (image) is on top and the second child (container) is below it.

![Portrait example](example/screenshots/Mobile.jpg)

---

### 2. Landscape/Desktop Layout
> On Landscape/Desktop Screen the image is on the right, container on the left.

![Landscape example](example/screenshots/MobileLandscape.jpg)

---

### 3. Row -> Column Switch
> If `LayoutPreference.Row` is selected, it will be a Row in portrait and Column in landscape. The first element in Row appears left in portrait, but in Column mode it moves to last; we want it last in column.

![Row to Column reversal gif](example/screenshots/ChildPlaced1st.gif)
  
---

### 4. Last Image in Row
> If we put the image last in Row, it appears last in Column (correct for landscape), but in Row layout it fails since the image should be first.

![Incorrect row order gif](example/screenshots/ChildPlacedLast.gif)

---

### 5. Custom ReverseDirection
> By choosing `ReverseDirection.Row` or `ReverseDirection.Column`, we get our customized behavior.

![Custom reverse direction gif](example/screenshots/DesiredOutput.gif)

---

## ☕ Support Me

If you find my work useful, consider supporting me:

[![Buy Me a Coffee](https://img.shields.io/badge/Buy_Me_a_Coffee-FFDD00?style=for-the-badge&logo=buy-me-a-coffee&logoColor=black)](https://buymeacoffee.com/shahnawazsx)

---

## License

MIT © Shahnawaz Khan
