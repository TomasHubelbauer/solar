# Shop

I have a little workshop room in my barn which is where my solar experimentation
started.

This system started off with this setup:

- Viking SCM135 135 Wp panel
- BYGD SPT-20A MPPT controller
- Goowei 6-DZM-20 12 V 24 Ah SLA battery

I got all of these components off Alza in order to put together a small POC.

Nowadays it sports and upgraded controller and battery:

- Viking SCM135 135 Wp panel
- Victron SmartSolar 100/15 MPPT controller
- SOK 12 V 206 Ah LFP battery

The controller upgrade is there as I am gearing up to introduce a 4 panel series
array which will need a beefier controller like the one I got and the battery is
there for the same reason as the new array should deliver more punch.

This is what the system will look like once I install the new panels I got:

- Victron 175 Wp 4s1p
- Victron SmartSolar 100/15 MPPT controller
- SOK 12 V 206 Ah LFP battery

I also have an order of two battery gauges in transit and I will install these
to be able to monitor both the capacity and the voltage of the battery at the
same time.

- [ ] Get the battery gauge delivered

The solar panel produces 135 W at peak sun cover.
Assuming a four hour peak sun cover, that's 540 Wh in a day.
The battery capacity is 200 Ah * 12 V = 2400 Wh.
This means we can replenish 20 % of the battery capacity every day.
I am powering three 5 W car bulbs for 24 hours a day off it currently.
That's 15 W a day.
Disconnected from the solar panel and at full capacity, the battery could power
this load for 2400 Wh / 15 W = 160 h = 6 days.
In a day, the full 24 hours, the bulbs consume 15 W * 24 h = 360 Wh.
Since the panel produces 540 Wh in ideal conditions and around 380 Wh with the
70 % factor, its production should just about cover this load consumption each
day.
Theoretically, the system should be able to run continuously forever, then.

Yet, it died after less than a week, almost exactly as if the battery was not
even charging in the first place.

- [ ] Figure out what happened with the charge controller once I am at the barn

With the four new panels in 4s1p I'd be getting 800 W * 4 h = 3200 Wh a day.
With the 70 % factor, that's 2240 Wh.
The battery capacity is 2400 Wh so the new system should be able to cycle or
very close to cycle the battery every day.

And if that turns out to be correct and working, I should be able to use those
2400 W each day across various loads including a 12 V DC to 230 V AC inverter.

| Image | Link |
|-|-|
| ![](viking-135wp.png) | [Viking SCM135 135 Wp][viking-scm135] |
| ![](bygd-spt-20a.png) | [BYGD SPT-20A][bygd-spt-20a] |
| ![](goowei-6-dzm-20.png) | [Goowei 6-DZM-20 12 V 24 Ah SLA][goowei-6-dzm-20] |
| ![](victron-100-15-mppt-bt.png) | [Victron SmartSolar 100/15 MPPT BT][victron-100-15-bt] |
| ![](sok-battery.png) | [SOK 12 V 205 Ah LFP][sok-12v-206ah] |
| ![](victron-175wp.png) | [Victron 175 Wp][victron-175wp] |
| ![](battery-gauge-percentage.png) | [AliExpress battery gauge (percentage mode)][battery-gauge] |
| ![](battery-gauge-voltage.png) | [AliExpress battery gauge (voltage mode)][battery-gauge] |

[viking-scm135]: https://www.alza.cz/viking-solarni-panel-scm135-d7240974.htm
[bygd-spt-20a]: https://www.alza.cz/bygd-solarni-regulator-nabijeni-spt-20a-d6959818.htm
[goowei-6-dzm-20]: https://www.alza.cz/auto/goowei-energy-6-dzm-20-baterie-12v-24ah-electric-vehicle-d6217380.htm
[victron-100-15-bt]: https://www.naradihned.cz/solarni-regulatory-victron-energy/mppt-solarni-regulator-victron-energy-smartsolar-100-15
[sok-12v-206ah]: https://www.europe.sokbattery.com/product-page/marine-grade-12v-206ah-lifepo4-battery-sealed-plastic-box-bluetooth-built-in-he
[victron-175wp]: https://www.solar-eshop.cz/p/fv-panel-victron-energy-175wp
[battery-gauge]: https://www.aliexpress.com/item/1005001763596519.html
