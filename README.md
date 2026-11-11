# Neo-Varangian
An alternate-history mod for Crusader Kings III that expands Norse adventuring. Kings can launch Varangian Ventures of their own, Normans can reclaim their Norse warrior heritage, and Norse or Norman rulers can seize Constantinople and found a **Varangian Empire** in place of the Latin one.

- **Game version:** 1.20.1.2
- **DLC:** *Northern Lords* is needed for the Grand Varangian Venture and the Norman decision. The Varangian Empire needs no DLC.
- **Saves:** start a new game. The mod adds a new empire title, which existing saves won't have.
- **Compatibility:** no base-game files are replaced. Everything is new content (prefixed `nv_`), so it should sit alongside most other mods.

## Features

### Grand Varangian Venture
A king-sized version of the Varangian Adventure war.

- **Kings only.** Counts, dukes, emperors and hegemons can't use it.
- **Same requirements as the normal venture:** the Varangian Adventurers innovation, Tribal era, prestige level, and a target that doesn't border you.
- **Once per lifetime.** It's used up when you declare, win or lose; your heir gets their own chance.
- **Bigger army.** It counts your same-culture, same-faith counties in mainland Scandinavia up to 20, where the normal venture stops at 10. At full strength that's about 3,700 men-at-arms and 3,000 levies.
- **Cost:** 1,000 prestige, the same as the normal venture.
- **Victory:** the conquered duchy becomes a new kingdom named after it, so conquering Normandy creates the Kingdom of Normandy. Your old kingdom is left behind and its lands go independent.

### Remember the Northmen (Norman decision)
The head of the Norman culture can add the **Coastal Warriors** tradition, which unlocks Varangian Veterans, Vigmen, Bondi and Huscarls.

- It's added on top of existing traditions, with no re-hybridizing and no swapping out another tradition.
- **Cost:** 1,000 prestige, half the usual cost of adopting a tradition.

### The Varangian Empire (Nordokratia / Normanokratia)
A Norse alternative to Frankokratia. It doesn't need a Catholic crusade, so pagan Norse can found it too.

1. **Plan the Taking of Miklagard** (decision). Available to an independent Norse or Norman king or emperor at prestige level 2 while a Byzantine Emperor exists. Costs 150 prestige and unlocks the war.
2. **The war.** It's called *Nordokratia* for Norse rulers and *Normanokratia* for Normans. You fight the Byzantine Emperor for one Byzantine kingdom.
   - **Win:** you found the Varangian Empire and move your capital there, to Constantinople if you hold it. The empire is Feudal and never Administrative.
   - **Your homeland is left behind.** It goes to a close relative as an independent realm, chosen from your children first, then siblings, then other family. Your main heir is skipped so the two realms stay separate. If no relative fits, the homeland breaks apart.
   - **Lose:** you have to take the decision again to try once more.
3. **Legitimize Varangian Dominion** (decision). The empire starts with no de jure land. Each use moves one Byzantine kingdom you control into it, with the same requirements as the Latin Empire's version.
4. **Expunge Varangian Dominion** (decision). Greek, Orthodox and Roman rulers can return Varangian kingdoms to Byzantium.
5. **Seize Imperial Duchy (Varangian)** (war). The base-game Seize Imperial Duchy only recognises the Latin Empire, so this is a separate version with the Varangian Empire in the Latin Empire's place. Like the original, both sides can use it to take duchies:
   - **The Varangian Emperor and vassals** can seize Byzantine or Varangian de jure duchies from anyone outside their realm. They gain dread and gold, as Latins do.
   - **The Byzantine Emperor, their vassals and Greek/Orthodox loyalists** can take back duchies from the Varangian realm.
   - **Anyone else in the old empire, such as Turks or Bulgarians,** can use it only while Byzantium has no Emperor, as with the original.
   - Unlike the original, it stays available for as long as the Varangian Empire exists, not just during a Byzantine collapse. Every war must involve the Varangian Empire, so it never duplicates the base-game war.

If the Varangian Empire falls, its kingdoms return to Byzantium automatically.

## Tuning
Most balance numbers are easy to find:

| What | Where |
|---|---|
| Grand Venture army size and prestige cost | `common/script_values/nv_grand_varangian_venture_values.txt` |
| Norman decision cost | `common/decisions/nv_norman_decisions.txt` |
| Varangian Empire decision costs and requirements | `common/decisions/nv_varangian_dominion_decisions.txt` |
| Which cultures count as Norse, Norman or Byzantine loyalist | `common/scripted_triggers/nv_varangian_dominion_triggers.txt` |

## File overview

```
common/
  casus_belli_types/       nv_grand_varangian_venture.txt, nv_varangian_dominion_wars.txt
  coat_of_arms/            nv_coat_of_arms.txt           (Varangian Empire arms)
  customizable_localization/ nv_custom_loc.txt           (Nordokratia / Normanokratia naming)
  decisions/               nv_norman_decisions.txt, nv_varangian_dominion_decisions.txt
  landed_titles/           nv_landed_titles.txt          (e_varangian_empire)
  on_action/               nv_on_actions.txt             (yearly clean-up of a fallen empire)
  script_values/           nv_grand_varangian_venture_values.txt
  scripted_effects/        nv_varangian_dominion_effects.txt
  scripted_triggers/       nv_varangian_dominion_triggers.txt
events/                    nv_varangian_dominion_events.txt
localization/english/      nv_neovarangian_l_english.yml, nv_varangian_dominion_l_english.yml
```

Localization files must be saved as UTF-8 **with BOM**, or CK3 won't load them.

## Known limitations
- The mod is untested in a full playthrough. If something misbehaves, check `Documents/Paradox Interactive/Crusader Kings III/logs/error.log` for lines mentioning `nv_`.
- English localization only.
- Founding the Varangian Empire is player-only, so the AI can never claim it before you. Once it exists, the AI uses the Legitimize, Expunge and Seize Imperial Duchy options normally.
- AI kings can use the Grand Varangian Venture under the base-game venture's AI rules. Expect the occasional AI king to abandon their homeland.
