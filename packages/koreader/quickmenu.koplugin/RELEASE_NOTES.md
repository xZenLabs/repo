# 2.0

<p align="center">
<img width="50%" alt="screenshot" src="https://github.com/user-attachments/assets/17c41540-d06e-4652-95ca-126f1417c71f" />
</p>

 New feature :

- Shadow ( inspire from [federico1176-wq](https://github.com/federico1176-wq) ).

    - Can be toggle for each section with "Show shadows". 

    - Can modify Offset (in px) and  Intensity (0 white / 1 full black) in style.

- Footer. 

    - Add "Show on all tab" : false -> change footer only on quickmenu tab / true -> change footer on all tab)

    - When  "Show on all tab" = false : the menu page nav arrow are remove in custom footer so there is more space for action.

- Info now use Bookshelf font if install and try to mimic Bookshelf **default** look.

- Quickmenu settings in koreader menu have icons like gear dialog.

- Add Vietnamese translation ( thanks to [toolbykien](https://github.com/toolbykien) )


Fix :

- When "Tap and gestures"+"Activate menu>"+"Auto-show bottom menu" -> true : Close both top and bottom menu in reader . Bottom menu use to block custom action in reader . It's not the case anymore.

- When "Tap and gestures"+"Activate menu>"+"Auto-show bottom menu" -> true : Quickmenu doesn't max out the number of item in top menu.

- Refresh background on some button

- Fix footer behavior. For example, in v1.9 footer gear dialog only show modification if you were on quickmenu tab.

# 1.9

Back from "holidays" (restore an apartment).
I use alpha during this month, seems stable and complete, so not much in this release :

- update patch for zenslider to prevent non working drag
- few cosmetic rework on menu to be consistent

For me Quickmenu does the job as an improve and stable version of Quicksetting. So not much to expect in the future except bug fix.

# 1.9-alpha

WARNING: This is an alpha release. Please stay on version 1.8, which is currently stable.

I will be on "holiday" for the next month, so this alpha will not be updated in the near future (desktops are great, but not very portable!). I just wanted to share the latest progress:

- Added LocalSend and FileBrowserPlus support.
- zenSlider are more integrated (lost center label but it's by design) and show warmth in %
- You can now reorder sections.
- There is a new settings panel (hold the QuickMenu tab to access it).

<img width="747" height="934" alt="image" src="https://github.com/user-attachments/assets/5fc10577-87d5-494f-80ae-8ace9a2a8d4b" />

There isn't much to see on the surface, but under the hood, it is a whole different beast. This is the problem with learning how to code while building a project: with better skills, you find new solutions (which is good), but you end up having to refactor a lot of your existing code (which is not fun).

WARNING: This is an alpha release. Please stay on version 1.8, which is currently stable.

# 1.8

- Footer override defaults one especially page turning. Correct it the best way i find...
- Align Warmth label
- Align ZenSlider label and option to center label (as they are in zenui)
- Add de, es, fr, it, ja, pt, ru

# 1.7

- Quickmenu now use its own setting file BREAKING change
- Add footer from zen ui, harder than anticipated...

Time to make documentation, testing and promotion
