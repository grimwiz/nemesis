# nemesis.ash

The Nemesis Quest script by slyz, with later updates by ckb1, taken from its SourceForge SVN repository
(`https://svn.code.sf.net/p/slyz-nemesis/code`, last commit r12 on 2016-04-10). That repository is no longer updated,
so fixes are carried here.

Install in KoLmafia (it needs zlib):

```
git checkout https://github.com/grimwiz/nemesis.git
```

If you installed the SVN version, remove it first with `svn delete slyz-nemesis`.

## Changes from r12

- The filthy child leash counts as familiar equipment that deals damage, so it's swapped off before fighting mother
  hellseals (its damage ruins their parts).
- Out of adventures mid-quest, it eats and drinks for more and carries on: `nemesis_diet` (default `autosea diet`, used
  only if [autosea](https://github.com/grimwiz/autosea) is installed; set it to another command, or to nothing to
  stop as before).
- It fights your Nemesis instead of stopping at the solved Volcano Maze. Before the fight it gears for HP and Moxie
  (plus spell damage for Pastamancers and Saucerors, or your main stat otherwise), keeps your Legendary Epic Weapon on,
  and restores HP and MP. A Pastamancer's Spaghetti Demon only uses its 200-325 damage special attack when it isn't
  entangled, and entangling it takes two casts of Entangling Noodles, so it casts Noodles twice, then makes one attack,
  and repeats; it heals with Lasagna Bandages below 350 HP. KoLmafia allows Entangling Noodles only once a fight, so
  those rounds are sent to the game directly. If a fight was left unfinished, running it again carries on with it. The other classes' demons are fought with your own combat settings. If you lose, run
  it again: the demon is still waiting at the centre of the maze.
- Once the quest is done, it collects your class's Legendary Regalia tattoo while the pieces still exist (some are
  quest items lost at the next ascension). If the Pretentious Artist's quest isn't done this ascension it does that
  first: the paint from the Sleazy Back Alley, the palette from the Haunted Pantry, the paintbrush from the Outskirts of
  Cobb's Knob. Running `nemesis.ash` again after the quest is finished just does this step.
- At the Nemesis' Lair it prints what KoLmafia sees before and after each fight (`[nemesis]` lines), retries a fight
  that KoLmafia didn't pick up through fight.php, and stops after three fights in a row that spend no turn, instead of
  asking for the same fight over and over.

Run it as `nemesis.ash`: plain `nemesis` does nothing in KoLmafia.

Instructions for the script itself: http://kolmafia.us/showthread.php?4761
