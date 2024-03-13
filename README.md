# MarvelCDB CLI

Command-line interface for viewing decks and decklists.

By default mcdbcli prints the deck sorted by aspect and pack.

## Options

-d : Print a deck by id

```sh
mcdbcli -d 677339
```

-l : Print a decklist by id

```sh
mcdbcli -l 36680
```

-r : Print in release order

Without -d or -l arguments `mcdbcli` will read deck as JSON from stdin

```sh
curl -s https://marvelcdb.com/api/public/decklist/36680 | mcdbcli
```

## MarvelCDB API

mcdbcli options only support public APIs. To print your private decks you need to fetch them
using the OAuth API yourself, and feed the JSON to mcdbcli via stdin.

## Example

Print a popular decklist:

```console
$ mcdbcli -l 13922
Wild Tutor - Adam Warlock
=== Hero cards ===
1 × Pip the Troll (Wave #4 The Mad Titan's Shadow #32)
1 × Soul World (Wave #4 The Mad Titan's Shadow #33)
1 × Karmic Staff (Wave #4 The Mad Titan's Shadow #34)
1 × Warlock's Cape (Wave #4 The Mad Titan's Shadow #35)
2 × Cosmic Ward (Wave #4 The Mad Titan's Shadow #36)
2 × Mystic Senses (Wave #4 The Mad Titan's Shadow #37)
3 × Karmic Blast (Wave #4 The Mad Titan's Shadow #38)
2 × Cosmic Awareness (Wave #4 The Mad Titan's Shadow #39)
2 × Quantum Magic (Wave #4 The Mad Titan's Shadow #40)
=== Aggression cards ===
1 × The Power of Aggression (Wave #1 Core Set #55)
1 × Drop Kick (Wave #1 Hulk #14)
1 × Martial Prowess (Wave #1 Hulk #18)
1 × Magic Attack (Wave #4 The Mad Titan's Shadow #43)
=== Justice cards ===
1 × The Power of Justice (Wave #1 Core Set #62)
1 × Concussive Blow (Wave #1 Ms. Marvel #31)
1 × "Think Fast!" (Wave #3 Drax #31)
1 × Zone of Silence (Wave #4 The Mad Titan's Shadow #50)
=== Leadership cards ===
1 × The Power of Leadership (Wave #1 Core Set #72)
1 × "Welcome Aboard" (Wave #3 Venom #27)
1 × Kaluu (Wave #4 The Mad Titan's Shadow #14)
1 × Summoning Spell (Wave #4 The Mad Titan's Shadow #55)
=== Protection cards ===
1 × The Power of Protection (Wave #1 Core Set #79)
1 × Tackle (Wave #1 Ms. Marvel #15)
1 × Brother Voodoo (Wave #1 Doctor Strange #12)
1 × Shield Spell (Wave #4 The Mad Titan's Shadow #61)
=== Basic cards ===
1 × Nick Fury (Wave #1 Core Set #84)
1 × Energy (Wave #1 Core Set #88)
1 × Genius (Wave #1 Core Set #89)
1 × Strength (Wave #1 Core Set #90)
1 × The Sorcerer Supreme (Wave #1 Doctor Strange #26)
1 × The Power in All of Us (Wave #2 Wasp #24)
1 × Spiritual Meditation (Wave #2 Scarlet Witch #19)
1 × Deft Focus (Wave #3 Galaxy's Most Wanted #24)
1 × Gamora (Wave #3 Drax #20)
```

Print a popular decklist in release order:

```console
Wild Tutor - Adam Warlock
=== Wave #1 ===
1 × The Power of Aggression (Aspect: Aggression Core Set #55)
1 × The Power of Justice (Aspect: Justice Core Set #62)
1 × The Power of Leadership (Aspect: Leadership Core Set #72)
1 × The Power of Protection (Aspect: Protection Core Set #79)
1 × Nick Fury (Aspect: Basic Core Set #84)
1 × Energy (Aspect: Basic Core Set #88)
1 × Genius (Aspect: Basic Core Set #89)
1 × Strength (Aspect: Basic Core Set #90)
1 × Tackle (Aspect: Protection Ms. Marvel #15)
1 × Concussive Blow (Aspect: Justice Ms. Marvel #31)
1 × Brother Voodoo (Aspect: Protection Doctor Strange #12)
1 × The Sorcerer Supreme (Aspect: Basic Doctor Strange #26)
1 × Drop Kick (Aspect: Aggression Hulk #14)
1 × Martial Prowess (Aspect: Aggression Hulk #18)
=== Wave #2 ===
1 × The Power in All of Us (Aspect: Basic Wasp #24)
1 × Spiritual Meditation (Aspect: Basic Scarlet Witch #19)
=== Wave #3 ===
1 × Deft Focus (Aspect: Basic Galaxy's Most Wanted #24)
1 × Gamora (Aspect: Basic Drax #20)
1 × "Think Fast!" (Aspect: Justice Drax #31)
1 × "Welcome Aboard" (Aspect: Leadership Venom #27)
=== Wave #4 ===
1 × Kaluu (Aspect: Leadership The Mad Titan's Shadow #14)
1 × Pip the Troll (Aspect: Hero The Mad Titan's Shadow #32)
1 × Soul World (Aspect: Hero The Mad Titan's Shadow #33)
1 × Karmic Staff (Aspect: Hero The Mad Titan's Shadow #34)
1 × Warlock's Cape (Aspect: Hero The Mad Titan's Shadow #35)
2 × Cosmic Ward (Aspect: Hero The Mad Titan's Shadow #36)
2 × Mystic Senses (Aspect: Hero The Mad Titan's Shadow #37)
3 × Karmic Blast (Aspect: Hero The Mad Titan's Shadow #38)
2 × Cosmic Awareness (Aspect: Hero The Mad Titan's Shadow #39)
2 × Quantum Magic (Aspect: Hero The Mad Titan's Shadow #40)
1 × Magic Attack (Aspect: Aggression The Mad Titan's Shadow #43)
1 × Zone of Silence (Aspect: Justice The Mad Titan's Shadow #50)
1 × Summoning Spell (Aspect: Leadership The Mad Titan's Shadow #55)
1 × Shield Spell (Aspect: Protection The Mad Titan's Shadow #61)
```

## Caching

mcdbcli caches the loaded cards to your home directory under `~/.mcdb/cards`. To remove the cached cards run the following command

```sh
rm -rf ~/.mcdb
```
