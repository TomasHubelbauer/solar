# Barn

This seems like the most complicated system I have in mind, because I have 380 V
machines in the barn that seems like they will be harder to support on a battery
bank than grid power.

Maybe they make good enough inverters to make this real or maybe I will end up
replacing these machines with 230 V counterparts as they are all old and it is
possible that nowadays you can get just as capable tools that don't require a
380 V outlet.

## Status

TODO

## Sizing

I want to power these machines and tools, barring any replacements that will not
require wall power (battery-powered tools):

- table saw
- band saw
- planer
- plasma cutter
- laser cutter
- angle grinders
- log splitter
- wood chipper
- garden tool outlet (lawnmower, strimmers)

The barn roof size is approximately 10x4 m (not an exact measurement).
The Victron 175 Wp panels that I have are 150x67 cm in size.

If I had two rows of panels, leaving some gaps for airflow to keep the panels
cool, I could get something like this:

- Roof height: 400 cm
- Panel height (1 row): 150 cm
- Panel height (2 rows + gap): 150 + 15 + 150 = 315 cm
- Rows: 400 cm - 315 cm = 2 rows
  - 15 cm gap
  - 400 - 315 / 2 = 85 / 2 = 42.5 cm margin
- Roof width: 1000 cm
- Panel width (1 column): 67 cm
- Panel width (1 column + gap): 80 cm
- Panel width (2 columns + gap): 67 + 80 = 147 cm
- Panel width (3 columns + gaps): 80 * 2 + 67 = 227 cm
- Panel width (4 columns + gaps): 80 * 3 + 67 = 307 cm
- Panel width (5 columns + gaps): 80 * 4 + 67 = 387 cm
- Panel width (6 columns + gaps): 80 * 5 + 67 = 467 cm
- Panel width (7 columns + gaps): 80 * 6 + 67 = 547 cm
- Panel width (8 columns + gaps): 80 * 7 + 67 = 627 cm
- Panel width (9 columns + gaps): 80 * 8 + 67 = 707 cm
- Panel width (10 columns + gaps): 80 * 9 + 67 = 787 cm
- Panel width (11 columns + gaps): 80 * 10 + 67 = 867 cm
- Panel width (12 columns + gaps): 80 * 11 + 67 = 947 cm
- Columns: 1000 cm - 947 cm = 12 columns
  - 13 cm gap
  - 1000 - 947 / 2 = 53 / 2 = 26.5 cm margin
- Panels: 12 columns * 2 rows * 2 sides = 24 * 2 = 48

````
                1000 cm roof width
┏━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━┓
┃ 40 cm vertical margin · 16 cm horizontal margin ┃
┃ ┏━┓ ┏━┓ ┏━┓ ┏━┓ ┏━┓ ┏━┓ ┏━┓ ┏━┓ ┏━┓ ┏━┓ ┏━┓ ┏━┓ ┃
┃ ┃ ┃ ┃ ┃ ┃ ┃ ┃ ┃ ┃ ┃ ┃ ┃ ┃ ┃ ┃ ┃ ┃ ┃ ┃ ┃ ┃ ┃ ┃ ┃ ┃
┃ ┗━┛ ┗━┛ ┗━┛ ┗━┛ ┗━┛ ┗━┛ ┗━┛ ┗━┛ ┗━┛ ┗━┛ ┗━┛ ┗━┛ ┃
┃     15 cm vertical gap · 13 cm horizontal gap   ┃ 400 cm roof height
┃ ┏━┓ ┏━┓ ┏━┓ ┏━┓ ┏━┓ ┏━┓ ┏━┓ ┏━┓ ┏━┓ ┏━┓ ┏━┓ ┏━┓ ┃
┃ ┃ ┃ ┃ ┃ ┃ ┃ ┃ ┃ ┃ ┃ ┃ ┃ ┃ ┃ ┃ ┃ ┃ ┃ ┃ ┃ ┃ ┃ ┃ ┃ ┃
┃ ┗━┛ ┗━┛ ┗━┛ ┗━┛ ┗━┛ ┗━┛ ┗━┛ ┗━┛ ┗━┛ ┗━┛ ┗━┛ ┗━┛ ┃
┃ 40 cm vertical margin · 16 cm horizontal margin ┃
┗━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━┛

67 cm panel width
┏━┓
┃ ┃ 150 cm panel height
┗━┛
```

Illustration using https://en.wikipedia.org/wiki/Box-drawing_character.

- Panel is 175 Wp & 3800 CZK
- 48 panels is 8.4 kWp & 180k CZK
- Possible wirings:
  - 12s4p = 12 * 20 = 240 V per series, 40 A in parallel
    - 240 V is okay for the panels, they have a 1000 V limit for each chain
    - 240 V is too much for the solar charge controller, 100 V is the limit
    - Maybe https://eshop.neosolar.cz/mppt-solarni-regulator-victron-energy-smartsolar-250-60-tr
    - But it says for 12 V the FV max is 860 Wp
    - Also Isc cannot exceed 35 A
  - 4s12p = 4 * 20 = 80 V per series, 120 A in parallel
    - Maybe https://eshop.neosolar.cz/mppt-solarni-regulator-victron-energy-smartsolar-150-100-tr-ve-can
    - Voc cannot exceed 150V which is okay here (80 V)
    - Isc cannot exceed 70 A which is not okay here (120 A)
    - Wp cannot exceed 1450 Wp for 12 V whih is not okay here (8400 Wp)
  - Multiple solar charge controllers in one system - see VE.can daisy chaining
  - Mutliple systems:
    - 4x 12s1p 240 V 10 A
      - https://eshop.neosolar.cz/mppt-solarni-regulator-victron-energy-smartsolar-250-70-tr
      - Isc cannot exceed 25 A which is okay here (10 A)
      - Voc cannot exceed 250 V which is risky here (240 V but what abou cold?)
      - 12 panels is 12 * 175 Wp = 2100 Wp
      - Wp cannot exceed 1000 Wp which is not okay here
