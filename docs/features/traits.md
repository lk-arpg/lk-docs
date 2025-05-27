# Traits

Traits are used as add-ons to [characters](characters.md) that describe their unique features. They can be edited in the admin panel by users with the **Edit World Data** [power](user-ranks.md).

## Usage

Traits and trait categories can be created in the admin panel, with the option of restricting them to certain [species](species.md). Once created, they can be attached to characters and [MYO slots](myo-slots.md).

The character and MYO slot masterlist pages contain options to filter characters by a trait or combination of traits.

Note that in the code, traits are named "features" instead as "trait" is a reserved keyword in PHP.

## Editing

### Categories

Editing trait categories and traits requires the **Edit World Data** power.

Trait categories can be created in the admin panel, with the usual category properties:

- Name
- World Page Image
- Description (accepts HTML)

The image and description are displayed only on the world page. Categories are optional, but allow traits to be listed in a controllable order on the character's page.

### Traits

Traits themselves have the following properties:

- Name
- Rarity
- World Page Image
- Trait Category
- Species Restriction
- Description (accepts HTML)

**Name** is the trait name which is displayed on the trait index.

**Rarity** is the [rarity](rarities.md) of the trait. While this is mostly cosmetic, a rarity cap can be set on MYO slots - users will only be able to submit the slot for approval with traits equal or lower to that rarity.

The **World Page Image** is shown in the encyclopedia, and nowhere else. As with all encyclopedia images, the recommended size is 200 x 200 pixels, but can be any size. It is recommended to use a simple thumbnail image for this image, and elaborate on trait restrictions, reference images etc. in the description area.

**Trait Category** is the category to which the trait falls under, and used for organisation. It is otherwise optional.

**Species Restriction** sets the trait to only be available for that particular species, and is optional.

**Description** is a description of the trait for the encyclopedia page.

## See Also

- [Characters](characters.md)
- [MYO Slots](myo-slots.md)