[[Was dormant for a while; refreshed 18 AUG 2026 against a live 352-toon farm — see [Field report](#field-report-a-352-toon-farm-18-aug-2026) for measured numbers and the mistakes that cost the most.]]

# Retainer-Guide
Plans and tips for making (many) retainers in FFXIV  
by Friendly

***still heavily work in progress***

To find things easily, use the Outline or Ctrl + F  
![image](https://github.com/user-attachments/assets/e44bc4d0-d814-4494-8fbb-d1a8990fed8e)


# Getting started
The process of making retainers has a lot of components. It'll take months, but it'll set you up for life. Don't think too much about time or trying to get it perfect the first time. I made this with help from many others so that you can have an easier time than we did. Just do what you can and if you change your mind, you can always level a new class or start over on a different server knowing that it'll be easier after the first. You can do a test toon before you commit, you'll learn a lot.

## Overview
The overall process can be broken down into these parts:  
Please note you don't have to finish one step on all toons before starting the next one.  
- Figure out your goals: This is one of the most important tasks of them all. How many toons? Do you want submersibles too? Choose accordingly.
- Level toon to 50 (47 is enough in practice if you're stopping Questionable there — see [Field report](#field-report-a-352-toon-farm-18-aug-2026))
- Make retainers
- Level retainer job and retainers to 100
- **Unlock GC rank 6** — not optional, see [GC ranks](#gc-ranks). Automated Expert Delivery refuses to run below it, and Expert Delivery is what funds your ventures.
- (Optional) Unlock GC rank 9 (duck bones)
- (Optional) Make FC

## Resources
[Punish plugins](https://discord.com/channels/1001823907193552978/1272173416933494875): AutoRetainer, SomethingNeedDoing, Lifestream, and more. They'll be mentioned as needed.  
[Henchman repo](https://raw.githubusercontent.com/Knightmore/Henchman/main/repo.json): make retainers, complete hunt log (was a planned feature as of 22 JUN 2025 — check the repo for current state before relying on it)

***Warning: as of 17 JUN 2025 old SND scripts must be used in SND Legacy or be rewritten for the new SND.*** Still true as of 18 AUG 2026 — plan on Legacy for anything you copy off an older guide.  
(Optional)[F.U.T.A.](https://github.com/McVaxius/dhogsbreakfeast/tree/main/AutoRetainer%20Companions/F.U.T.A) retainer manager, levels FSH via ocean fishing, does turnin  
[Wiggly/Friendly scripts](https://github.com/WigglyMuffin/SNDScripts/tree/main/Scripts/)
 - Character Cycler: Runs a script on a list of characters before AutoRetainer can do it
 - (Optional)Overseer: retainer/sub manager, uses gc missions to level any DoL and trades mats between accounts to do so.
 - Questionable Companion: for nearly all issues that stop Questionable from completing an alt
 - (Optional)AutoHunt: does your (GC) hunt log and dungeons/quests and ranks up to the rank 9 for duck bones

Plugins the farm actually runs day to day, added 18 AUG 2026:
 - **[ChilledLeves](https://github.com/CheatingChild/ChilledLeves)**: the whole leve loop. Picks up, turns in, and repeats fisher leves. This is what does 1→89 FSH.
 - **AutoHook** (puni.sh) + **DistantSeas**: ocean fishing. AutoHook does the casting off presets, DistantSeas tracks the route/results.
 - **Questionable** + **Questionable Companion**: MSQ/class quests to whatever level you stop at.
 - **Lifestream**: teleports. Everything above assumes it's installed.

## Glossary  
ar: AutoRetainer  
ad: Autoduty  
fc: Free Company  
gc: Grand Company  
post-process: AR can do a few things after it finished a toon, such as starting a script. See the end of [Setup](#setup) for more.  
qst: Questionable  
qv: Quick Venture  
snd: SomethingNeedDoing  
sub: Submersible (in FC workshop)  
toon: Character  
turnin: exchanging gear for seals via Expert Delivery. Deliveroo used to do this; it's built into AR now, so there's nothing extra to install.  

## Practical considerations
### How many toons to make  
Generally speaking you want enough to fill an hour even at the best times. TLDR: make 40 and adjust as needed.  
If you wanna think ahead, you can measure (with a stopwatch or script) how quickly you log in and process retainers on a given DC (or use my numbers from an old pc as a start) and use this formula:
> 3600/(relog_time+(retainers*(retainer_processing_time)) = no. of toons
>
> I've made a [lil tool](https://claude.ai/public/artifacts/c58325eb-961d-47e6-9147-0008be30611a) to check your numbers, the total retainers you get can be multiplied by the gil breakdown in [Numbers and stuff](#Numbers-and-stuff).

My numbers:
> 3600/(55+retainers*6) = no. of toons

_Note: the 6 s here is an older measurement — [Speed](#speed) breaks it down as 7.5 s per retainer plus 1.16 s of amortised turnin. Use 8.5-9 s if you want the pessimistic estimate, and re-measure on your own machine either way._

Your overall processing time will vary due to login queue, fps, ping and what other management tasks AR is doing, but whatever the formula gives you is a good estimate.

### Subs
If you want subs, you should look for a server with housing availability. Check [PaissaDB](https://zhu.codes/paissa) and/or ask sublords in #housing-deployables in the Punish discord.

### FCs
You can skip making FCs for your new toon if you don't need subs, but I'd recommend doing it anyway cause you'll then get an extra ~20% gil by selling company credits via cereleum tank at some point. You'll ofc need a 2nd acc for a month to make the FCs. See [Numbers and stuff](#Numbers-and-stuff).

### Login time
Unless you're playing on a dead server, chances are you'll mostly have a 30s queue time. If you don't wanna min/max, I recommend choosing the server with the best ping. If you want to potentially save time on login, and don't mind checking some stuff, read further.  

Login time works like this:  If there's no queue, you get in. Otherwise the game updates the queue in 30s. So, wether the queue is 1 or 100, you're still waiting 30s. If there's no queue, then you don't wait. Waitingway tracks login queues, you can find the data [here](https://grafana.camora.dev/d/adkjhur7scc1sf/waitingway?orgId=1&refresh=5m) (page takes a while to load and you need to scroll down).  
Select the data you need at the top, time should be something sensible like 7 days and find the graph titled Queue Size for your DC of interest, click icon in the top right corner, inspect, Data, download csv.  
To interpret that csv data file I 'made' a [lil tool](https://claude.ai/public/artifacts/ef71b600-aaa9-412a-bdde-10314a6bfbbb). Pull the csv file into it and it'll give you the average login times.  
Mind you these numbers are not accurate, because the sample from Waitingway is more populated near busy times. But it's still good for a relative comparison.  
Now - _before you all flock to OCE_ - AR and manual things that you want to do will take longer due to ping which somewhat counteracts the time save on login. For me personally from EU that basically means I save next to nothing by being on OCE, but your mileage may vary.  
For the sake of convenience you can find the login time of the last 30 days as of 17 JUN 2025 [here](#login-times) — these have not been re-pulled since, so treat them as relative comparison only

### Entry subscription
You can get away with 8 toon/DC, but you'll be limited to ~30 toons so I'd get as many retainers as you can afford (except maybe the premium app one). If you plan on having 4 or fewer retainers/toon, I'd recommend upgrading your subscripion as you'll have a bunch of downtime within an hour.

### Starting resources
Some parts of the retainer making process can be made faster with gil or gathering, namely getting green gear for seals at the start and buying leve fish/GC delivery&supply mission items.  
You can gather them yourself (via retainers even) and pay for a 2nd account to trade these from your main; or ask for help on Discord. More on how much of what you need is detailed in their respective sections, but it's worth starting ASAP if you don't have the gil to throw at the problem.

## Setup
Plugins: Dalamud Plugin Installer - Settings - Experimental - scroll down - Custom plugin repositories. Add the repo links to a new line, press plus, click save. Then install the plugin from the installer.  
Extra for SND Legacy: While you're there, you'll need to enable testing builds  

![image](https://github.com/user-attachments/assets/cdaac55c-a7cd-4238-bba1-908cc1669568)

Once you have SND installed, right click, get the testing version 
![image](https://github.com/user-attachments/assets/274dba6c-0f55-4b59-8689-8f48311b71f7)

Scripts: These will tell you usually in both the script itself and on the github page what they need. Read the requirements and don't forget to set the settings within the script.  
For setting config folder for AutoHunt: Open SND. Click help, click options on the help window.  
![image](https://github.com/user-attachments/assets/bbd6f2f7-a80d-4797-a5d9-2c1e92acfa7d)  

You can also set a script to run after AR under the AutoRetainer option.  
![image](https://github.com/user-attachments/assets/aae37fb7-ae46-45d7-a50e-a770840f35d1)

# Road to 50
## Toon creation
You can make 8 toons/day. If there's an automatic way to do this, I'll update this, until then, just do them manually in whatever way you see fit.  
Marauder is recommended for now because it gets stuck the least in early quests, but if things change I'll update this. I would not worry too much about the name or the look of toons, except to make them blend in. The standard names are likely taken, so if you run out of ideas just change a letter or two. Random look is ok.

## Unlocking retainers
Henchman takes care of unlocking retainers. More on how to use them in [Retainer Management](#retainer-management).   
## Onto level 50
Qst and companion script should take you to 50. There are a few places where it _currently_ gets stuck (such as solo duties), but once we've figured out the new snd, it should be easy enough to fix.  
You can set a level limit in qst companion to switch to the next toon at 50.   
## GC ranks
You will need seals, later ranks also need the GC hunt log 1&2. Seals are best collected via Expert Delivery. Until you have it unlocked, you should use CBT's Enforce Expert Delivery option. (This predates AR folding Deliveroo in; AR's own rank-check override is described below, and is the more likely thing you'd reach for now.)

**Get every toon to rank 6, and treat it as mandatory rather than a nice-to-have (added 18 AUG 2026).** AutoRetainer will not run Expert Delivery below GC rank 6 — the check is `GetRank() >= 6` and it is the first thing `CanExpertDeliver()` tests, before any of your delivery triggers are even looked at. Below rank 6 the plugin quietly does nothing at the GC forever: no turnin, no seal spending, no venture purchases. It does not warn you.

There *is* an override — `/ays set IgnoreGCRankCheck true`, also in AR's Advanced/Debug section as "Ignore GC rank check for MM delivery" — but AR's own troubleshooting page lists it as a **misconfiguration** and tells you to turn it off for normal operation. Treat it as a diagnostic, not a fix. Rank up instead.

This is the single most expensive thing in this guide to get wrong, because the farm looks healthy the whole time it's happening. See [Field report](#field-report-a-352-toon-farm-18-aug-2026).
# Leveling your retainer class

## Botanist/Miner

Untested here — this farm went all-in on Fisher, so I have no measured numbers for it. What's worth knowing before you pick:

- A retainer can only be assigned a class **you have unlocked yourself**, and its level is **capped by your own highest level in that class**. Levelling the retainer means levelling yourself first, always.
- The class decides what it can bring back. MIN/BTN are the pick if you want specific sellable mats or you're feeding submersible builds; combat classes return monster parts (meats, skins) gatherers can't touch.
- **Changing a retainer's class permanently destroys the EXP it accumulated on the old one.** In practice this is a one-way decision — make it before you sink ventures into anything.

If you've done MIN/BTN at scale, tell me and I'll write this section properly.

## Fisher

Fisher is faster and/or cheaper than any other class to do. The downside is that it has basically no use outside of quick ventures. If you have no subs and don't care about getting/selling specific valuable mats then this is your class.

### 1-30

You unlock FSH in Limsa, do your class quests till you unlock ocean fishing, then start with the Limsa leves.

**Answered 18 AUG 2026:** it's the Limsa levemete **Tmokkri** (NPC `1000970`), fisher leves, run until 30. Fish come from the vendor (Lominsan Anchovy, finger shrimp, coral butterfly), so no retainer supply needed for this stage. Take **two leves per bracket** here — unlike Costa, you're not budgeting a scarce fish, so grabbing both is a straight time save.

Priority order (highest first, and priority order *is* the accept-fallback order — take the top one being offered, else the next):

| Prio | Leve |
|-|-|
| 4 | The Fertile Incandescent |
| 2 | Adventurers' Relish / Poor Boys Eat Well / They Taste Just as Pretty / Splendor in the Glass |
| 1 | Soup to Guts / A Kelping Hand / Cloud Cutlet |
| skip | Yummy in the Tummy, Fish by Many Other Names, Just Add Water, Brain Candy |

Under 40 leves was the right guess.

### 30-90: Costa Leves
For the main bulk of levelling, the ~~best~~ popular way is to get fish with retainers and use them for Costa Del Sol leves.  
3/4 fish can be gathered with retainers. To get the max yield you want your gathering retainers geared — still need to pin down the exact item/vendor, so treat this as "buy the best FSH main hand you can hand them" for now.  
> If you don't have any, you can ask others to sell it to you in #housing-deployables or find my listings on Sophia (OCE) (DM/tag me if sold out).

![image](https://github.com/user-attachments/assets/bd82c03a-8ce7-4b45-885d-5d539c6801f3)  

For this you'll need 156 leves with preferred world bonus, double that without.
<details>
    <summary>Details</summary>
    Average leve is 50% × Black Sole XP(+100% if preferred world) × 3 + 50% × other XP(+100% if preferred world) <br>  
    50% × 206492 × 200% × 3 + 50% × 344153 × 200% = 963629<br>
    XP from 30 to 90 is 150168400<br>
    150168400 / 963629 = 155.8363229 leves   
</details>  

_Friendly note: you can stop at an earlier level, since you'll need to do the rest with ocean fishing and there's some leeway in there before you need a new boat for lvl 100 (or you can top up your xp with GC delivery missions)_  

Prioritise Black Sole in ChilledLeves.  
Since 1/6th of the time you can choose between Tuna and Herring their ratio can vary between 2:1 and 1:2.

**Answered 18 AUG 2026:** ChilledLeves' leve priorities *are* the fallback order, so you set it once and the ratio takes care of itself. Levemete **Nahctahr** (NPC `1004344`), fisher, run until 89:

| Prio | Leve | Fish |
|-|-|-|
| 3 | Kitchen Nightmares No More | Black Sole |
| 2 | A Recipe for Disaster | Ash Tuna |
| 1 | Just Call Me Late for Dinner | Indigo Herring |
| skip | The Blue Period | Sea Pickle |

**Turn off grab-two-per-bracket for this one.** The fish counts below are budgeted against exactly that fallback order with *one* leve taken per visit — taking two at once burns your top *and* second-choice fish in the same trip and blows the budget.  
But, the flexibility is good cause Tuna can be gathered faster with retainers, so make you AR venture plan like so.  
![image](https://github.com/user-attachments/assets/6514a076-b631-4433-961c-5ed26bd675e7)  

If you're going all the way, you'll need 156 Ash Tuna, 78 Indigo Herring, 702 Black Sole per alt; 6240, 3120 and 28080 per 40 alts.  
If you're not gathering, you can buy either fish as long as both are at least 78 and add up to 234.  

### Any level: Ocean Fishing
If for some reason leves are no longer viable for you, either cause you've hit 90, don't have fish or gil to buy it or anything else, ocean fishing is a good way to level.  
Every 2 hours you can do it for 22 min, use F.U.T.A or some other script to start it when it's up and fish with AutoHook from puni.sh using the presets.  
The downside is it's only every 2 hours, so solely relying on this for levelling will add about day per toon until you're done, but it is completely afk at least.  
![image](https://github.com/user-attachments/assets/6c9f87ef-742b-48dc-a4b8-6b00bf3bc3f1)

## Combat
The least automatic of the 3. All I can say is run Qst and companion script till it doesn't work anymore and be prepared for a lot of manual piloting.  
Cons:   
    - Takes the most manual work (crystal tower+wherever msq isn't fully auto)  
    - Takes the longest time (~5 days/toon)  
Pros:  
    - Opens up income streams (everything non-ARR: daily maps, EW leves, doman enclave, high lvl ventures)      
    - Free retainer gear (high iLvl makes HQ items from qv more likely, targeted ventures for combat classes)  
    - Alts for raiding  
It's the path least taken, if you have advice for those that choose this, let me know and I'll expand this section.

# Retainer management

## The seal -> venture loop is the whole engine

Your retainers run on **venture tokens**. Tokens come from the Grand Company Quartermaster; the seals to buy them come from Expert Delivery turnin. AR drives both halves. Understand this loop before you tune anything, because when it stops it stops *silently*.

**Good news first: you do not have to configure the purchase.** AR appends Ventures to your GC exchange list automatically as the final fallback — it buys them up to a 65,000 cap once nothing else on your list can be bought. An empty exchange list is a perfectly fine setup and means "spend everything on ventures". You only need to touch that list (Inventory Management, *Grand Company Delivery / Exchange Lists*) if you want something *other* than ventures bought first.

**What actually stops the loop** is AR deciding not to go to the GC at all. Every one of these must be true or the whole thing is skipped, in this order:

1. **Multi Mode Expert Delivery is enabled** — AR Inventory Management, *Grand Company Delivery / General Settings*, checkbox "Enable Multi Mode Expert Delivery".
2. **The toon is GC rank 6 or higher.** Hard gate, checked before anything below it. See [GC ranks](#gc-ranks) — this is the one that bites.
3. **There is deliverable gear in the inventory.** No gear, no trip. This matters more than it sounds: gear comes from quick ventures, so if tokens are already at zero there's nothing being farmed to hand in.
4. **A trigger fires** — either free inventory slots drop to your threshold, or (if you've enabled "deliver on venture exhaust") the venture count falls below your set number. Set the venture trigger. Inventory-only means a farm with plenty of free space never refills its tokens.

Conditions 2, 3 and 4 interact into a deadlock you can't get out of by waiting: no tokens -> no quick ventures -> no gear returned -> nothing deliverable -> no GC trip -> no tokens. Once a farm falls into that hole it stays there with a growing pile of unspendable seals. Breaking out needs an outside push — buy tokens by hand on a few toons, or hand in any gear you can scrape together, to restart the cycle.

Symptoms you're in it:
- Seal balances rising instead of hovering near zero.
- Venture counts in single digits across most toons.
- AR disabling toons on its own — a toon with no tokens has nothing to do, so it drops out of rotation. Fleet-wide it looks exactly like a plugin bug. It isn't one.

Your seal cap also rises with GC rank, so a low-rank farm wastes income faster whenever it stalls.

## Hiring them in the first place

[Henchman](https://raw.githubusercontent.com/Knightmore/Henchman/main/repo.json) does the Retainer Vocate interaction, so hiring is not the manual slog it looks like — that's why [Unlocking retainers](#unlocking-retainers) hands you off to here. Its `Retainer Vocate` config lives per-client alongside its other job folders, so a client that has run it once can be copied to the rest.

Two things to settle *before* you let it loose, because both are effectively permanent:

- **Which class.** A retainer needs a class and an equipped main arm before it can venture at all, you can only assign a class you have unlocked yourself, and changing class later **destroys the EXP the retainer accumulated on the old one**. See [Leveling your retainer class](#leveling-your-retainer-class).
- **How many slots you actually have.** Two per character are free. Up to seven more are paid add-ons, plus one via the Companion App — 9 with add-ons, 10 with the app. The catch: **paid slots are per service account, shared across every character on it.** They follow the account, not the character, so on an account holding 32 toons buying slots does *not* multiply by 32. Price that out before you commit to a retainer count in the [formula](#how-many-toons-to-make).

## Keeping inventory under control

Turnin needs *deliverable gear* in the bag, and quick ventures return plenty of junk that isn't. Two AR lists to know:

- **Unconditional Sell List** — anything on it gets vendored no questions asked. Fastest way to populate it is right-clicking an item and picking "+ Add to Unconditional sell list"; there's also a bulk adder at Inventory Management, *Inventory Cleanup / Fast Addition and Removal*.
- **Quick Venture Sell List** — same idea, scoped to QV returns. Items already on the unconditional or discard lists won't be added here.

Anything worth less than ~20-50k belongs on a sell list. Left alone, a full inventory blocks turnin, and blocked turnin is a stalled farm — see the deadlock above.

## Retainer levels

Retainers gain EXP only from ventures, and cap at **your own** level in their class. So the order is: level yourself, then feed tokens, then the retainers climb. If tokens dry up the retainers freeze wherever they are — and the gil-per-QV numbers in [Numbers and stuff](#numbers-and-stuff) assume level 100 retainers, so a farm stuck in the 60s is earning well under what the maths promises.

## Bells and parking

Retainer work only happens at a Summoning Bell, which is why every AR routine is location-bound. Inn rooms are the reliable option (no housing needed, no wandering players). Park toons at a bell before you expect AR to process them, or you're paying teleport time on every single relog.

# Miscellanious

## How many Ocean Fishing boats from 1-100?
 
Strongly recommended to go on boats at 80+ or even 90 while using costa leves from fish from retainers. But if you can't find/make the fish needed, here's how I'd do it.
With preferred world bonus, I did it with about 20-26 total leves (to ~lvl 45) plus 18ish boats. Without leves its about 23 boats.
Starting limsa leves till level 20 using fish bought from vendor (Lominsan Anchovy, finger shrimp and coral butterfly).
Quarrymill leves to lvl 45-50 (or 30 with Costa leves) (all but black ghost are usually ok price).
Then ocean fish to 100. Things that help - in order of importance - cordials, rng, gp from gear, food.
A typical result without anything looks like  1 - 11 - 21 - 31 - 39 - 45 - 50 - 55 - 59 - 63 - 67 - 70 - 73 - 76 - 79 - 82 - 85 - 88 - 90 - 92 - 94 - 96 - 98 - 100

## Field report: a 352-toon farm (18 AUG 2026)

Everything above was written while building this. Here's what the farm actually looks like now, measured off the AutoRetainer configs rather than remembered — including the parts that went wrong, which are the useful bit.

### What exists

| | |
|-|-|
| Toons | **352** — 11 clients x 32, one service account each, ~8 toons per world across 4 worlds |
| Worlds | Cerberus 88, Phantom 88, Sagittarius 87, Omega 72, Moogle 14, Louisoix 3 |
| Retainers | **704** — exactly 2 per toon, **all Fisher** |
| Toon FSH level | 90-96, median **93** |
| Toon MRD level | **47** on 328/352 (the deliberate Questionable stop) |
| Retainer level | median **69** (420 at 69, 198 at 70, full range 40-78) |
| GC rank | **3** on 351/352 |
| FCs | **0** |
| Subs | **0** |
| Gil | 78.4M total, median 215k/toon |
| Seals banked | **2,442,988** |
| Venture tokens held | **2,204 across the whole fleet** |

So: the hard part is done. 352 toons levelled, 704 retainers hired and classed, the leve pipeline ran to completion. And the farm is currently earning close to nothing.

### What went wrong

**Every toon is GC rank 3. AutoRetainer's Expert Delivery requires rank 6.** That's it. That's the whole thing.

`CanExpertDeliver()` tests the rank before it looks at any of your delivery triggers, so on all 352 toons it returned false every single time, forever. No GC trip, no turnin, no venture purchase. The exchange settings were all correct — Multi Mode Expert Delivery on, venture-exhaust trigger on at 20, ventures auto-appended as the fallback purchase. All of it downstream of a gate that never opened.

I originally diagnosed this as an empty exchange item list. That was wrong — an empty list means "spend everything on ventures", which is what I wanted anyway. The config was never the problem. The rank was.

The damage in numbers:

- Venture sends per day peaked at **12,382** (31 JUL), held ~10k/day through early August, and fell to **424** on 17 AUG. That's ~3% of peak. The farm was living off a token stockpile the whole time and slowly eating it.
- **334 of 352 toons hold fewer than 4 venture tokens. 94 hold zero.**
- 2.44M seals sat unspendable. At 200 seals a token that's **~12,200 ventures** — a full day of peak fleet output, earned and paid for, never collected.
- **179 of 352 toons had disabled themselves in AR.** A toon with no tokens has nothing to do, so AR drops it from rotation. It reads exactly like a plugin bug. It is not a plugin bug.
- Once tokens hit zero the deadlock locked: no tokens -> no quick ventures -> no gear -> nothing deliverable -> no GC trip. Even at rank 6 that last loop would have needed an outside push to restart.

Nothing in any log said "you are not buying ventures". No warning fired for being under the rank requirement. The only visible signal was seals going up instead of down — which is the one thing that looks like success.

**Second-order damage:** retainers earn EXP from ventures only, so they're frozen at level ~69 against a level-93 ceiling. Every gil-per-QV figure in [Numbers and stuff](#numbers-and-stuff) assumes level 100 retainers, so actual take is well under the projection until the tokens flow again and the retainers catch up.

### Gaps still to close

Roughly in order of gil-per-hour-of-effort:

1. **Get all 352 toons from GC rank 3 to rank 6.** Nothing else on this list matters until this is done — it's the gate holding the entire income loop shut. Rank-ups cost seals, and there are 2.44M sitting there, so the backlog pays for its own fix.
2. **Then break the deadlock by hand**: the rank gate opening isn't enough on its own, because zero tokens means no gear to deliver. Buy tokens directly on a batch of toons to restart quick ventures, then re-enable the 179 self-disabled toons and let the loop take over.
3. **Retainers 69 -> 93.** Free once tokens flow — it's just venture EXP — but it takes real calendar time, so the sooner tokens come back the sooner the QV yields match the maths.
4. **Toons 93 -> 100 FSH.** Leves are done at 89; the rest is ocean fishing (or topping up with GC delivery missions). See [How many Ocean Fishing boats](#how-many-ocean-fishing-boats-from-1-100).
5. **Rank past 6 once the loop is running.** Rank also sets the seal cap, so a low cap keeps wasting income every time the farm stalls. Rank 9 (duck bones) stays optional.
6. **Retainer slots: still 2 per toon, no add-ons in use.** Read the slot economics before buying — extra slots are **per service account, shared across every character on it**, so on a 32-toon account this does *not* multiply by 32. Worth pricing properly against the ~20% from the next item.
7. **0 FCs, 0 subs.** That's the ~20% gil from selling company credits via ceruleum tank left entirely on the table, plus every submersible route. Needs a second account for a month to found them.
8. **19 market board listings across 704 retainers.** Everything's being vendored. Fine as a deliberate choice, but it is a choice — see the AR unconditional sell list advice in [Turnin](#turnin).

### The lesson worth stealing

The failure wasn't a crash, it was an **unmet precondition that never announced itself**. Relogs worked. Leves worked. Every setting I'd have thought to check was correct. The farm was rank 3 against a rank 6 requirement from the day it was built, and it ran fine for weeks anyway — on a stockpile — so the symptom showed up long after the cause, which is the worst possible ordering for debugging.

Two things I'd do differently:

**Check the preconditions, not the settings.** I verified the exchange config repeatedly and it was right every time. The gate was one function call upstream of everything I was looking at. When a feature does nothing, find what has to be true before it runs, and test *that* first.

**Alarm on outputs you expect to move, not processes you expect to run.** Seals climbing is plausible on its own. Token counts falling is plausible on its own. Together they're the entire diagnosis — and no log line was ever going to put them side by side for me.

## Info on rankings
Based on my toons with 9 retainers you cap out on ~1.2m seals/week or 5.2m /month. That lands you around 10th place for gc ranking on low pop OCE servers, and only lower anywhere else.

## Numbers and stuff:

_All figures below assume level 100 retainers. Below that the yields are lower — see [Field report](#field-report-a-352-toon-farm-18-aug-2026) for what a stalled farm actually earns._

Gil per quick venture (7.25):
SE decided OC should give you old expensive items :'( This means while ppl are farming that, the price of dyes went down by 30-50%. You can still sell them if you want or hold onto your venture coffers until the price goes back up.

720 = 1200 x 0.6 from seals
1745 = 3% x 9.7% x 2 x 300k from dyes
2465/qv or 1.80m/month

If you wanna spend time selling fc points, they are worth 1-2 gil via **cereleum tank**. you can get 2 depending on buyer, but for simplicity, let's say 1. Don't buy anything else with them to sell, there's no market.
529 = 529 x 1 fc points
2994/qv or 2.19m/month

Gil per quick venture (7.2):
720 = 1200 x 0.6 from seals
2910 = 3% x 9.7% x 2 x 500k from dyes
3630/qv or 2.65m/month

With FC points: 529 = 529 x 1 fc points
4159/qv or 3.04m/month

On top of this you will also get items to sell, most of which are going to be vendored, because it's a hassle to sell manually. Just add anything worth less than 20k-50k to your AR sell list.

### Speed
Your handling time will depend on a bunch of factors: login queue, AR settings and enabled features, ping, fps. But ballpark figures for me on an old pc are: 
Relog: avg. 55 seconds (40-80 s), retainer: avg. 7.5 s, or 70 s total for 2 retainers. Turnin takes 1.16 s/retainer, more on this below. So with a 40x2 army you should complete a cycle in less than 48 minutes (40* (55 +2 * (7.5+1.16))/60) which means you can fit more retainers into an hour.

If you're slower than these numbers, minimise your game and try to raise fps, disable unused plugins (via collections).

#### Turnin
Again, depends, so ballpark. With proper inventory management (ie. AR unconditional sell list and periodic cleaning) you need turnin after about 750 qv (inventory + armory is 530 slots, some used for stuff to be sold makes it ~500, with ~66% of getting turnin gear, that'll fill in 750 qv). Turnin takes about 15 min, that's 1.16 s (15 x 60/750) for each qv. With only 2 retainers you should need it every 15.6 days (750/2/24). With more retainers, it's more frequent, but even with 10 total retainers it'll be an extra 11.6 s which is ~9% of the expected runtime of 130 s (55+10 x 7.5).
There's actually a reason to do it more frequently, since items from last patch have a higher chance of dropping, which are worth more seals. I don't know the maths on this, and I don't think it's really worth digging into, but there may be merit to doing turnin more frequently, like right after your armoury is full. It won't eat into your efficiency.


#### Login times

EU/Light

![image](https://github.com/user-attachments/assets/7762ad04-2bd7-4e47-8265-2e006d5805a7)

EU/Chaos

![image](https://github.com/user-attachments/assets/31f17dfd-a3be-4983-85a1-8fa4a46575be)

NA/Aether

![image](https://github.com/user-attachments/assets/b713d72e-2b00-4374-a62e-122ef53f627e)

NA/Primal

![image](https://github.com/user-attachments/assets/f0bd658f-4e07-4f0e-af27-830fe1df5841)

NA/Crystal

![image](https://github.com/user-attachments/assets/69825381-463e-47ac-a3d7-a6fcc57bca42)

NA/Dynamis

![image](https://github.com/user-attachments/assets/34e82bd8-1972-4d23-986c-091a499ea120)

JP/Elemental

![image](https://github.com/user-attachments/assets/be8fd9c4-f2f8-45e5-a7ba-4e03a5358100)

JP/Gaia

![image](https://github.com/user-attachments/assets/885e51d0-eb19-4f0e-a2db-a541a7ff137e)

JP/Mana

![image](https://github.com/user-attachments/assets/d6c778f4-5d1b-4fec-b88d-b76a1c19a260)

JP/Meteor

![image](https://github.com/user-attachments/assets/9808eb0b-0526-4315-8891-066279232292)

OCE/Materia

![image](https://github.com/user-attachments/assets/99762d26-820c-485a-9d6a-8a30584ca2a7)
