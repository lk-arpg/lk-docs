# Loot Tables

Loot tables are used to randomise rewards during distribution. They can be edited in the admin panel by users with the **Edit World Data** [power](user-ranks.md) and are the only type of world data that cannot be publicly viewed.

## Usage

Loot tables must be created before they can be distributed as a reward.

After they have been created, they can be attached to the following:

- Prompt rewards
- Box type items
- Another loot table

Loot tables can be nested, chaining multiple loot tables to form a complex item selection system. Nesting many loot tables is not recommended, however, and care must be taken to avoid creating an infinite rolling loop.

Upon claiming the reward (having a prompt approved, or opening a box type item) the final reward will be rolled accordingly. Each loot table will select only ONE (1) of the rewards attached to it.

## Editing

Loot tables require the following:

#### Name

This is the name used to identify the table internally. This name will only be shown in the admin panel when editing rewards; users will not be able to see this name, so it is recommended to make it descriptive to make loot table selection easier.

#### Display Name

This is the name that users will see, if a random reward will be given as a prompt reward. Users without the appropriate power are not able to see the rewards of a loot table as well as the odds, so you may want to choose a name that's appropriately cryptic depending on how transparent you would like to be about the rewards. (e.g. "A Random Prize" vs. "Item A OR Item B")

#### Loot

Under this section, you can choose the rewards that can be given out through this table. The following loot types can be selected:

- Item
- Item Category
- Any items of given raritie(s) (optional)
    - Enable in the extensions [config file](config-files.md)
- Any items of given raritie(s) in an item category (optional)
    - Enable in the extensions [config file](config-files.md)
- Currency
- Loot table
- None (no reward given)

Additionally, you can specify the quantity and rolling weight.

Quantity is fairly straightforward, giving a fixed amount of the item or currency selected. In the case of loot tables, it rolls the loot table that number of times. For example, if you selected Loot Table A with a quantity of 2, it would roll Loot Table A 2 times, rather than once and double the reward.

Weight represents the likelihood of the reward being selected. This is not a percentage (which is calculated in the Chance column) and does not have to add up to 100, although that may make it easier to keep track of.

## Test Rolling

The loot table editing page provides a feature to generate test results for a loot table. Note that if the loot section has been edited, it must be saved beforehand for the changes to take effect. Additionally, if "None" is selected as a possible reward type, it will not show up as a result (so fewer results than rolls selected may be generated in this case).

## See Also

- [Items](items.md)
- [Currencies](currencies.md)
- [Prompts](prompts.md)
- [How Random is Random?](randomness.md)