Draft of gameplay changes for improved balance and historicity
aimed at a version 2.0 of the Advanced Civ mod (AdvCiv) for Civ IV: BtS.
Parts of this document might still be adopted by AdvCiv, but, by and large,
this project has been abandoned for being not only too ambitious but also
unsatisfactory (at least) in its handling of the early game.
---
tech-tree.pdf: The proposed tech tree
stat-changes.pdf: All other changes to game data (units, buildings ...)
Rationales in footnotes.
Those specific changes were to be accompanied by some general rule changes.
See the numbered list at the end of this file.
---

Post-mortem:
Over time, my biggest gripe with BtS has become its fantastical presentation
of the world at game start as largely devoid of human habitation, roamed by
animals that behave like the carnivores in Jurassic Park and suffer nonsensical
penalties from attacking in their native terrain, wide-reaching exploration
conducted by scout units and "hunting" as a technology that only some civs are
privy to from the outset.

This bothers me more than some other fundamentally ahistorical design decisions
- all civs emerging in the same year, immortal leaders, no internal collapse,
no world-altering events to speak of, unit movement being extremely slow -
because those are straightforward results of representing the history of human
civilization as a wargame in the mold of Risk and making that game somewhat
balanced and fair, and, maybe more importantly, because those distortions
don't have much bearing on the player's turn-by-turn decisions. At a given
moment, the game can feel authentic, even if the long-term developments are
implausible and far too predictable. There are also already some optional rules
in AdvCiv - points assigned unequally in Advanced Start, the human player
taking over several AI civs over the course of a game - to address, to an
extent, some of those high-level misrepresentations.

The early game does not have much of an excuse for being outlandish,
and a mod could make significant improvements with modest means:
- Animals could be disabled by default (AdvCiv already has that option);
- more Tribal Villages could be placed, those some distance away from any
starting site usually guarded by a Barbarian Warrior in the beginning;
- the Scout unit could be removed or appear later as a Mounted unit;
- a strength-1 Barbarian "Raider" unit could force the civs to guard their
capitals and improvements rather than explore beyond the immediate
surroundings during the first 50 turns;
- the starting techs could be revised, replacing Hunting with, perhaps,
Animal Husbandry or a variant thereof.
Such changes, however, undercut the central idea of keeping the mod accessible
by starting in a highly familiar fashion and deviating substantially from BtS
gameplay only toward the midgame (e.g. when it comes to siege and
artillery units).

Realism Invictus is a good example of a mod that has overhauled the early game
and is not easy to adapt to. No one needs a second Realism Invictus.

The early-game tech tree is also still unsatisfactory in some other regards:
• Wheel should arguably not be a starting tech as wheeled transportation only
makes a big difference when combined with draft animals. Perhaps Road should
initially only represent unpaved trails that eliminate extra movement costs
from hills and vegetation and connect resources but don't reduce per-tile
movement costs to less than 1 until a project "Royal Road" has been created,
enabled by Masonry (can't really have Stone speed it up though if Stone is
supposed to have only a local effect).
• "Archery" is an awkward tech name. Can't really represent composite bows
either - those have an advantage mainly on horseback. Could perhaps re-theme
the tech as Taxation, Corvee, Militia or Conscription. That could cover the
Slavery replacement civic, which however shouldn't be available this early,
or Barracks, which would play well at an early tech but, going by the
building name, should really represent a professional army. Or name it
Fortification and enable Walls (faster with Stone via Masonry) in addition
to Archer. The devil is in the details with such ideas. Will also be difficult
to reassign the tech quotes suitably.
• "Smelting" isn't historically accurate in the second column. Should probably
be eliminated. Not clear where Spearman should go then; would be better for
gameplay not to bundle it with Axeman. And Trireme? Workshop should perhaps
cede its early-game production effect to Pasture, which would then be allowed
on non-resource tiles (on which tiles exactly? should access to Sheep or Cow
be required?). Could turn Workshop into an Industrial-era improvement,
representing remote work (workshop system).

(end of post-mortem/ open issues)
---

Proposal for general rule changes (not fully covered by the PDFs)

1. Combat system overhaul:
* Greatly reduce the number of collateral damage targets, the collateral damage limit and the damage limit of siege units (see stat-changes.pdf). Exempt some units from damage limits; e.g. let air units destroy ships.
* Only four units, chosen at random, are available for defense in each stack; the best defender is chosen from that subset. After each attack, another random defender becomes available. Prototype implementation:
https://github.com/f1rpo/AdvCiv/compare/master...f1rpo:defender-randomization
* Limited capacity of cities and Forts: No defensive bonus while stack size exceeds capacity.
* Limited number of attacks per turn against a single tile.
* Limited number of combat rounds, so that combat can end in a draw (like air combat).
* Limited free healing; when land units are badly damaged, some need to be disbanded in order to heal the others. Or some other cost on healing. Perhaps unlimited free healing for the AI, as a player handicap.
See also: https://forums.civfanatics.com/threads/advanced-civ.614217/page-5#post-15157996

2. Lower the production bonuses from traits and resources to 80%. Let production modifiers and special commerce modifiers apply to Processes (Wealth, Research, Culture), but halve both modifiers. Reduce the production-to-commerce conversion rate of Processes to 80%. Or perhaps set the rate based on the difficulty level.

3. Better scaling of Great Person effects (e.g. Discover ability, Trade Mission) with the game progress - currently too powerful in the early game and midgame. Revise the progression of birth thresholds. Settled Great People grant a free building (e.g. a Bank from a Merchant), but have a limited lifetime. Hurry-wonder mission for Great Prophet (religious wonders).

4. Much lower corporation yields overall; the yields per city decrease each time the corporation expands. No HQ required in order to train Executives, but increased maintenance (and/or some other handicap) when there is no HQ or when war or a civic makes it inaccessible.

5. Make resources less crucial for health and happiness as this disadvantages small civs too much by the mid/late game: Let a few more resources go obsolete (see tech-tree.pdf) and perhaps cap the total health bonus of buildings like Granary at 2 (not spelled out in stat-changes.pdf). Grant happiness from city culture rate (with diminishing returns) regardless of whether the culture slider is used; have the slider position only matter for Colosseum and Theater.
(Already implemented: The AI is willing to sell even non-surplus resources at reasonable prices when it doesn't need those resources for city growth.)

6. Civs running a state religion different from that of the Apostolic Palace (AP) can't be AP members. (Already implemented: partial members can be targeted by war votes.) The AP owner picks all proposals, no election of the AP resident. UN and AP voting populations are weighted by city nationality (i.e. relative city tile culture).

7. Increase the cost of drafting and balance it by adding or removing food to/from the city's food store in addition to population loss. And stricter checks and balances. Remove the whip ability of Slavery (see stat-changes.pdf).

8. Tech trading: Imparting a tech costs an amount of research points. Probably to be paid after the trade, blocking further research and tech trades in the meantime.

9. Tech diffusion based on culture in foreign city tiles (and other factors).

10. Limit nuclear explosions to a single tile. Units can't move/attack into a tile on the same turn that it was nuked.

11. Ravages of war: (Civ 4 Reimagined and Dawn of Civilization already do some of this.)
* Razing a city takes one attack per population; each attack reduces the population by one and has a chance of destroying a building.
* Reduced city defense causes anger; bombardment causes war weariness and has a small chance of destroying a building. Each attack against a city defender has a chance of destroying a building. Upon entering the city, few buildings or none are destroyed (unless razed).
* Reduce capture gold; perhaps only grant it when razing.

12. City garrisons need to have sufficient (defensive) combat strength in order to quell "fear for safety" anger. (Already implemented as change 500b, but currently disabled through an XML switch.) The Nationalism tech (to be renamed to "Nation State") disables "fear for safety" permanently.

13. Changes to finances:
* Fold inflation into increased costs for units, civics and cities; i.e. pay for having a lot of stuff, not for the game turn number.
* Add a small gold cost to air missions and airlifting.
* Stronger impact of upkeep class on civic upkeep costs.
* Overhaul of trade route profit modifiers (rewarding trade between coastal cities, even if on the same continent) and the matching of partner cities.

14. A slight waste effect when a commerce slider is in an extreme position (akin to Alpha Centauri) or a small cost for adjusting a slider.

15. Consider replacing most culture rate increases of buildings with a one-time boost to city culture. This would speed up the impact of buildings on tile culture (nationality).

16. Revise the AI leader personalities to match their historical counterparts a bit better and to have somewhat fewer leaders that are very peaceful and agreeable or very warlike and disagreeable.
