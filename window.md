# Window

I have a unused utility window in my apartment which is very narrow and faces in
an odd direction, so I figured instead of just boarding it up I'd build a small
system in it and see how it goes.

## Status

WIP

## Sizing

I don't really have a serious load in mind.
As of current, I am powering a lamp with the system and use it to charge my
phone sometimes.

## System

I bought the only 18 V panels on AliExpress that I was able to find that would
fit the window, though they do almost perfectly:

https://www.aliexpress.com/item/1005003123354268.html

I have 6 of them and they all provide 18 V at 5 W (I = P / V = 5 / 18 = .278 A)
and are wired in parallel so the whole array produces 18 V 1.7 A in theory.

I am using a PWM charge controller as MPPT seems like a complete overkill for
this use-case.
Also, I read online that PWM is good for purely parallel installations, which I
am not sure is true but this one happens to be one such so if it is, great.

https://www.alza.cz/bygd-solarni-regulator-nabijeni-pv2420u-d6959817.htm

The controller charges this little 12 V 7.2 Ah SLA battery:

https://www.alza.cz/auto/csb-evx1272-baterie-12v-7-2ah-d5597727.htm

In theory, the system should make 18 W 1 A, so in 4 hours of peak sun, 72 Wh.
The battery is 7.2 Ah at 12 V, that's 86 Wh.

So we should be just shy of cycling the battery every day with this system.

But in practice, due to the I guess side shade of the window frame or the bad
orientation of the panels, I never see more than 13 V hit the charge controller
and it seems to be able to top up the battery to 75 % going from 50 % charge.

So I think I can cycle 25 % of the battery capacity every day.

I also have another SLA battery at hand which I am not using for anything else
but without better panels or better wiring, there is no point in using it:

https://www.alza.cz/auto/goowei-energy-6-dzm-20-baterie-12v-24ah-electric-vehicle-d6217380.htm

I also have this LFP battery on order so that I can discharge the battery more
deeply if needed, but it is unlikely to top up much more than the SLA one.

https://www.aliexpress.com/item/1005002405783446.html

25 % of the usable (cyclable) capacity that I have is around 22 Wh.
I am powering an LED lamp off this system sometimes.
It eats up 5 W so it could run for 4 hours off this battery's 25 % capacity.

I am also thinking of powering a Pi Pico W off this system continuously.
I found online that it eats 1 mA in sleep and 100 mA while running.
It operates at either 3 or 5 V or I think even up to 9 A on the power pin?
I will need a buck converter anyway or I might just run it off the USB port on
the solar charge controller.

Let's pretend .1 A at 12 V (if I used a buck converter), so that's 1.2 Wh.
25 % of the battery capacity was 22 Wh so 22 Wh / 1.2 Wh is around 18 hours of
operation.

That's non-ideal as it would drain more of the battery than the system can
replenish over the course of the day.

I might be able to utilize sleep mode to bring the power down or use better
panels to get more solar power or use 2s3p over 1s6p wiring to maybe be more
resistant to shade and in turn also generate more power?

Possible candidate solar panels:

https://www.aliexpress.com/item/1005003956761039.html

The are a worse fit for the window and would be permanently covered by the
window frame at their horizontal edges but it might works out better overall?
120 Wh as opposed to the current 72 Wh if parallel.
