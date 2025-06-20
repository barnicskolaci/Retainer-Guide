# Retainer-Guide
Plans and tips for making (many) retainers in FFXIV
by Friendly

still heavily work in progress

# Sections
1. [Getting started](#Getting-started)
   - 1.1 [Overview](#Overview)
   - 1.2 [Resources](#Resources)
   - 1.3 [Glossary](#Glossary)
   - 1.4 [Practical Considerations](#Practical-considerations)
   - 1.5 [Setup](#setup)
2. [Road to 50](#road-to-50)
   - 2.1 [Toon creation](#Toon-creation)
   - 2.2 [Early levels](#Early-levels)
   - 2.3 [Unlocking retainers](#Unlocking-retainers)
   - 2.4 [Onto level 50](#Onto-level-50)
   - 2.5 [GC ranks](#GC-ranks)
3. [Leveling your retainer class](#Leveling-your-retainer-class)
   - 3.1 [Botanist/Miner](#Botanist/Miner)
   - 3.2 [Fisher](#Fisher)
   - 3.3 [Combat](#Combat)
4. [Retainer management](#Retainer-management)
5. [Miscellaneous](#Miscellaneous)



# Getting started
The process of making retainers has a lot of components. It'll take months, but it'll set you up for life. Don't think too much about time or trying to get it perfect the first time. I made this with help from many others so that you can have an easier time than we did. Just do what you can and if you change your mind, you can always level a new class or start over on a different server knowing that it'll be easier after the first. You can do a test toon before you commit, you'll learn a lot.

## Overview
The overall process can be broken down into these parts:
Please note you don't have to finish one step on all toons before starting the next one.  
- Figure out your goals: This is one of the most important tasks of them all. How many toons? Do you want submersibles too? Choose accordingly.
- Level toon to 50
- Make retainers
- Level retainer job and retainers to 100
- (Optional) Unlock GC rank 9
- (Optional) Make FC

## Resources
[Punish plugins](https://discord.com/channels/1001823907193552978/1272173416933494875): AutoRetainer, SomethingNeedDoing, Lifestream, and more. They'll be mentioned as needed.

Henchman repo: https://raw.githubusercontent.com/Knightmore/Henchman/main/repo.json

Warning: as of 17Jun2025 old SND scripts must be used in SND Legacy or rewritten for the new SND.  

(Optional)[F.U.T.A.](https://github.com/Jaksuhn/SomethingNeedDoing/tree/master/Community%20Scripts/AutoRetainer%20Companions/AutoMaintenance) retainer manager, levels FSH via ocean fishing, does turnin

[Wiggly/Friendly scripts](https://github.com/WigglyMuffin/SNDScripts/tree/main/Scripts/)
 - Character Cycler: Runs a script on a list of characters before AutoRetainer can do it
 - (Optional)Overseer: retainer/sub manager, uses gc missions to level any DoL and trades mats between accounts to do so.
 - Questionable Companion: for nearly all issues that stop Questionable from completing an alt
 - (Optional)AutoHunt: does your (GC) hunt log and dungeons/quests and ranks up to the rank 9 for duck bones
   
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


## Practical considerations

### How many toons to make
Generally speaking you want your toons to be processed in a little over an hour even at the best times. TLDR: make 40 and adjust as needed.

If you wanna think ahead, you can measure how quickly you log in and process reatiners on a given DC (or use my numbers from an old pc as a start) and use this formula:
```
3600/(relog_time+(retainers*(retainer_processing_time)) = no. of toons
my numbers 3600/(55+retainers*6) = no. of toons
```
Your overall processing time will vary due to login queue, fps, ping and what other management tasks AR is doing, but whatever the formula give you or 40 is a good estimate.

### Subs
If you want subs, you should look for a server with housing availability. Check [PaissaDB](https://zhu.codes/paissa) and/or ask sublords in #housing-deployables in the Punish discord.

### FCs

You can skip making FCs for your new toon if you don't need subs, but I'd recommend doing it anyway cause you'll then get an extra ~20% gil by selling company credits via cereleum tank at some point. You'll ofc need a 2nd acc for a month to make the FCs. See [Numbers and stuff](#Numbers-and-stuff).

### Login time
Unless you're playing on a dead server, chances are you'll mostly have a 30s queue time. If you don't wanna min/max, I recommend choosing the server with the best ping. If you want to potentially save time on login, and don't mind checking some stuff, read further.
Login time works like this:  If there's no queue, you get in and the game updates the queue every 30s. So, wether the queue is 1 or 100, you're still waiting 30s. If there's no queue, then you don't wait. Waitingway tracks login queues, you can find the data [here](https://grafana.camora.dev/d/adkjhur7scc1sf/waitingway?orgId=1&refresh=5m) (page takes a while to load and you need to scroll down). Select something sensible like 7 days at the top and find the graph titled Queue Size for your DC of interest, click icon in the top right corner, inspect, Data, download csv. Now, to interpret that csv data file I 'made' a [lil tool](https://claude.ai/public/artifacts/ef71b600-aaa9-412a-bdde-10314a6bfbbb). Pull the csv file into it and it'll give you the average login times.
Mind you these numbers are not accurate, because the sample from Waitingway is more populated near busy times. But it's still good for a relative comparison.
Now - before you all flock to OCE - AR, Deliveroo and manual things that you want to do will take longer due to ping which somewhat counteracts the time save on login. For me personally from EU that basically means I save next to nothing by being on OCE, but your mileage may vary.
For the sake of convenience you can find the login time of the last 30 days as of 17 JUN 2025 [here](#login-times)

### Entry subscription
You can get away with 8 toon/DC, but you'll be limited to ~30 toons so I get as many retainers as you can afford (except maybe the premium app one). If you plan on having 4 or fewer retainers/toon, I'd recommend upgrading your subscripion as you'll have a bunch of downtime within an hour.

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
IDK HOW THE NEW SND WORKS YET, I'LL UPDATE THIS AFTER I DO.

You can also set a script to run after AR under the AutoRetainer option.

![image](https://github.com/user-attachments/assets/aae37fb7-ae46-45d7-a50e-a770840f35d1)

# Road to 50

## Toon creation

## Unlocking retainers

## Onto level 50

## GC ranks

# Leveling your retainer class

## Botanist/Miner

## Fisher

Fisher is faster, or cheaper than any other class to do. The downside is that it has basically no use outside of quick ventures. If you have no subs and don't care too much this is probably your class.

### 1-30

You unlock FSH in Limsa, do your class quests till you unlock ocean fishing, then start with the Limsa leves. I'll need to check how ChilledLeves works to say what's best to get to 30, but it's gonna be some combination of leves. 

### 30-90: Costa Leves
For the main bulk of levelling, the best way is to get fish with retainers and use them for Costa Del Sol leves.
3/4 fish can be gathered with retainers. Prioritise Black Sole in ChilledLeves
![image](https://github.com/user-attachments/assets/628bb8a2-3def-4809-abaf-33a1511685fb)
Average leve is 50% × Black Sole XP(+100% if preferred world) × 3 + 50% × other XP(+100% if preferred world)

50% × 206492 × 200% × 3 + 50% × 344153 × 200% = 963629

XP from 30 to 90 is 150168400

150168400 / 963629 = 155.8363229 leves

So you'll need 156 leves, 2 rounds of turnin

156 Ash Tuna, 78 Indigo Herring, 702 Black Sole per alt; 6240, 3120 and 28080 per 40 alts.

Since 1/6th of the time you can choose between Tuna and Herring you can shift Tuna/Herring from 25:25 to 33:17 if you so choose.

This is good cause Tuna can be gathered faster with retainers, so make you AR venture plan like so.
![image](https://github.com/user-attachments/assets/6514a076-b631-4433-961c-5ed26bd675e7)

### Any level: Ocean Fishing

If for some reason leves are no longer viable for you, either cause you've hit 90, don't have fish or gil to buy it, or anything else, ocean fishing is a good way to level.
Every 2 hours you can do it for 22 min, use F.U.T.A or some other script to start it when it's up and fish with AutoHook from puni.sh using the presets. The downside is it's only every 2 hours, so solely relying on this for levelling will add about day per toon until you're done, but it is completely afk at least.
![image](https://github.com/user-attachments/assets/6c9f87ef-742b-48dc-a4b8-6b00bf3bc3f1)

## Combat

Just run Qst and companion script till it doesn't work anymore teehee.
No, but for real, I don't recommend this because it:
    - takes the most manual work (crystal tower+wherever msq isn't fully auto)
    - takes the longest time (like 5 days/toon)
    - doesn't give that much more for you (daily maps, EW leves, doman enclave, non qv rewards, free retainer gear)
    
If despite this you want to do it, more power to you. Some people enjoy doing multiple MSQ runs, some want mats from combat retainers.

# Retainer management

# Miscellanious

## How many Ocean Fishing boats from 1-100?
 
Strongly recommended to go on boats at 80+ or even 90 while using costa leves from fish from retainers. But if you can't find/make the fish needed, here's how I'd do it.
With preferred world bonus, I did it with about 20-26 total leves (to ~lvl 45) plus 18ish boats. Without leves its about 23 boats.
Starting limsa leves till level 20 using fish bought from vendor (Lominsan Anchovy, finger shrimp and coral butterfly).
Quarrymill leves to lvl 45-50 (or 30 with Costa leves) (all but black ghost are usually ok price).
Then ocean fish to 100. Things that help - in order of importance - cordials, rng, gp from gear, food.
A typical result without anything looks like  1 - 11 - 21 - 31 - 39 - 45 - 50 - 55 - 59 - 63 - 67 - 70 - 73 - 76 - 79 - 82 - 85 - 88 - 90 - 92 - 94 - 96 - 98 - 100

## Info on rankings
Based on my toons with 9 retainers you cap out on ~1.2m seals/week or 5.2m /month. That lands you around 10th place for gc ranking on low pop OCE servers, and only lower anywhere else.

## Numbers and stuff:

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

### Speed:
Your handling time will depend on a bunch of factors: login queue, AR settings and enabled features, ping, fps. But ballpark figures for me on an old pc are: 
Relog: avg. 55 seconds (40-80 s), retainer: avg. 7.5 s, or 70 s total for 2 retainers. Turnin takes 1.16 s/retainer, more on this below. So with a 40x2 army you should complete a cycle in less than 48 minutes (40* (55 +2 * (7.5+1.16))/60) which means your retainers are fully efficient and can fit more into an hour.

If you're slower than these numbers, minimise your game and try to raise fps, disable plugins.

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


Turnin: Again, depends, so ballpark. With proper inventory management (ie. AR unconditional sell list and periodic cleaning) you need turnin after about 750 qv (inventory + armory is 530 slots, some used for stuff to be sold makes it ~500, with ~66% of getting turnin gear, that'll fill in 750 qv). Turnin takes about 15 min, that's 1.16 s (15 x 60/750) for each qv. With only 2 retainers you should need it every 15.6 days (750/2/24). With more retainers, it's more frequent, but even with 10 total retainers it'll be an extra 11.6 s which is ~9% of the expected runtime of 130 s (55+10 x 7.5).
There's actually a reason to do it more frequently, since items from last patch have a higher chance of dropping, which are worth more seals. I don't know the maths on this, and I don't think it's really worth digging into, but there may be merit to doing turnin more frequently, like right after your armoury is full. It won't eat into your efficiency.
