<p align="center">
  <h1 align="center">dhof-loot</h1>
</p>
<p align="center">
<b><a href="https://github.com/anish-agnihotri/dhof-loot#About">About</a></b>
|
<b><a href="https://github.com/anish-agnihotri/dhof-loot#Derivatives">Derivatives</a></b>
|
<b><a href="https://github.com/anish-agnihotri/dhof-loot#License">License</a></b>
</p>

# About

This repository contains tooling and data for [Loot](https://www.lootproject.com/faq) and other derivative projects, and is free to use without credit or attribution, for any means.

The `/` directory contains scripts and data for Loot, and `/derivatives` contains the same for projects inspired from or built atop Loot.

> Loot itself is a collection of 8,000 unique bags of adventurer gear NFTs. At release, anyone could claim loot bags for just gas, and all bags were claimed in under 4 hours. Each loot bag contains 8 items: a piece for an adventurer's chest, foot, hand, head, neck, ring, waist, and weapon.

# Loot

## Distribution

- tokenIds `1` to `8000` by [Loot](https://etherscan.io/token/0xff9c1b15b16263c61d017ee9f65c50e4ae0113d7) 
- tokenIds `8001` to `16000` by [xLoot](https://etherscan.io/token/0x8bf2f876e2dcd2cae9c3d272f325776c82da366d)
- tokenIds `16001` to `24000` by [pLoot](https://etherscan.io/token/0x03ea00b0619e19759ee7ba33e8eb8e914fbf52ea)

## Output

- `output/loot.json` contains all tokenIds and their attributes.
- `output/occurences.json` contains the number of occurences by attribute.
- `output/rare.json` contains a mapping of `lootId` to `score` (which is the sum of number of occcrences of each child attribute for a `lootId`), sorted ascending by `score`. It also includes `rarest` which is how rare the loot bags attributes are (`1` == `rarest`, `8000` == `least rare`), based on this specific ranking mechanism.
- `output/probability.json` contains a mapping of `lootId` to `rank` by probabilistic occurence rather than rank (`P(A in bag at slot 1)` and `P(B in bag at slot 2)`, then `P(A in slot 1 and B in slot 2)` is the product of the 2 probabilities).
- `output/images.json` contains the base64 encoded SVG of each tokenId

## Run locally

```bash
# Install dependencies
npm install

# Collect all Loot
npm run collect

# Parse Loot statistics
npm run parse

# Collect Loot base64 encoded images
npm run images
```

To run derivative scripts, follow the README in their subdirectory.


# Credits

- [@ktasbas](https://github.com/ktasbas) for adding Loot base64 encoded SVG retrieval support
- `vance46#5648` and `UFvOgue, X-Divine Rober#8392` for helping me flag and think through the probablistic occurence for Loot items

# License

Loot is licensed under [The Unlicense](https://github.com/Anish-Agnihotri/dhof-loot/blob/master/LICENSE)—a license with no conditions whatsoever which dedicates works to the public domain.

Unlicensed works, modifications, and larger works may be distributed under different terms and without source code.
