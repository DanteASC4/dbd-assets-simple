<p align="center">
  <img src="https://static.wikia.nocookie.net/deadbydaylight_gamepedia_en/images/c/c7/Logo_dbd.png/revision/latest/scale-to-width-down/1000?cb=20210601173807">
</p>

---

- [Currently contains](#currently-contains)
  - [`killer_perks.json`](#killer_perksjson)
  - [`killers.json`](#killersjson)
- [Future Additions (maybe)](#future-additions-maybe)
- [Credit](#credit)


# Currently contains


**Killers**

Images for:

- Add-ons
- Perks
- Vertical Portrait (small)
- Horizontal Portrait (small)


**General**

- Blank perk icons
  - under  `/template/perks`


## `killer_perks.json`

```ts
/*
Data is one big object where each key is the perk name and the value is the above object type.
Reasoning: This makes it so once you have a perk name in mind that you want info about you don't need to search for it
*/
type AllData = {
  [n: string]: Perk;
}

/*
- description
  - Effect of the perk
- quote
  - Flavor text of the perk
- killer
  - "the killer_name" (or "All" for perks that all killers can unlock)
- url
  - direct link to png from repo
*/
type Perk = {
  description: string;
  quote: string;
  killer: string;
  url: string;
}


```

## `killers.json`

```ts
// Array of Killer type
type AllData = Killer[];

/*
- name
  - "the killer"
- addons
  - see type
- portraits
  - see type
- perks
  - array of each killer's three unique perks, can be used as keys for the perk data
*/
type Killer = {
  name: string;
  addons: AddOn[];
  portraits: Portraits;
  perks: [string, string, string];
}

/*
- name
  - name of the addon
- description
  - description of the addon's effect
- url
  - direct link to png from repo
*/
type AddOn = {
  name: string;
  description: string;
  url: string;
}

/*
Note:
- these are both relatively small
  - In the ~250-350 range
- horizontal images are not uniform size as poses differ slightly

- vertical
  - direct link to png of the killers vertical portrait from this repo
- horizontal
  - direct link to png of the killers horizontalportrait from this repo
*/
type Portraits = {
  vertical: string;
  horizontal: string;
}
```


# Future Additions (maybe)

Just some things I may or may not add at some point. If anyone has any other requests I'm open to that as well.

- Might switch `killers.json` to be similar to `killer_perks.json` in that it'd be an object where the key is the killername
- Survivor data
  - Perks
  - Items
    - Add ons
  - Portraits


# Credit

All this data & info came from the amazing wiki!