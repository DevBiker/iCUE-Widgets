# iCUE-Widgets
Repository for various iCUE widgets

## Sensor Graph Plus

A highly customizable graph widget for Corsair dashboard LCD screens (e.g. Xeneon Edge) that plots up to three sensors at once, with a secondary axis for mixing sensor ranges and units, plus rolling statistics for each sensor.

### Features

- **Up to three sensors** — Primary and Secondary sensors each get their own axis (left/right); an optional third sensor (Additional) shares the legend and can be plotted against either existing axis.
- **Dual axis support** — Primary Sensor plots on the left axis, Secondary Sensor on the right, so you can graph sensors with very different ranges/units (e.g. temperature °C alongside fan RPM) on the same chart without one flattening the other.
- **Per-sensor customization** — Each sensor gets its own label override, color, and axis min/max override (leave blank to use sensible defaults based on sensor type/kind/units).
- **Live legend with trend indicators** — Each sensor's legend entry shows its current value, connection state, and a trend arrow/rate computed over a fixed 1-minute window, independent of the chart/statistics windows.
- **Configurable chart window** — Slider (1–30 minutes) controlling how much history is drawn on the graph.
- **Configurable statistics window** — Separate slider (1–30 minutes) controlling the rolling average/min/max shown in the statistics area, independent of the chart window.
- **Full widget personalization** — Text color, accent color, background color, background image, background brightness, glass blur, and background transparency, matching the look of other widgets in this repo.
- **Graceful loading/empty states** — Shows "Loading sensors…", "Select a sensor in the widget settings.", or "Sensor unavailable" as appropriate instead of a blank chart.

### Usage

1. Install the widget and add it to a supported dashboard LCD screen surface in iCUE.
2. Open the widget's settings and, under **Widget Setup**:
   - Pick a **Primary Sensor** (defaults to a temperature sensor). Optionally set its label, color, and min/max axis bounds.
   - Toggle **Show Secondary Sensor** to add a second sensor (defaults to load %) plotted on the right axis, with its own label/color/min/max.
   - Toggle **Show Additional Sensor** to add a third sensor (defaults to a fan sensor). It doesn't get its own axis — use **Additional Sensor on Secondary Axis** to choose whether it's plotted against the Primary or Secondary axis scale.
   - Adjust **Chart Window** and **Statistics Window** to control how much history is graphed vs. how much history the averages/min/max are computed over.
3. Under **Widget Personalization**, adjust text/accent/background colors, optionally set a background image, and tune brightness, glass blur, and transparency to match your theme.
4. Leave any sensor's Min/Max field blank to let the widget auto-select a reasonable axis range based on the sensor's type, kind, and units.

Requires the `widgetbuilder.sensorsdataprovider:Sensors` plugin and a `dashboard_lcd` device with the `sensor-screen` feature (Windows only).
