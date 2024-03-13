# MarvelCDB CLI

Command-line interface for viewing decks and decklists.

mcdbcli prints the deck sorted by aspect and pack.

## Options

mcdbcli supports two options: `-d` and `-l`. Both options accept a single argument.

Print a deck by id

```sh
mcdbcli -d 677339
```

Print a decklist by id

```sh
mcdbcli -l 36680
```

Without any arguments `mcdbcli` will read deck as JSON from stdin

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
1 × Pip the Troll (The Mad Titan's Shadow #32)
1 × Soul World (The Mad Titan's Shadow #33)
1 × Karmic Staff (The Mad Titan's Shadow #34)
1 × Warlock's Cape (The Mad Titan's Shadow #35)
2 × Cosmic Ward (The Mad Titan's Shadow #36)
2 × Mystic Senses (The Mad Titan's Shadow #37)
3 × Karmic Blast (The Mad Titan's Shadow #38)
2 × Cosmic Awareness (The Mad Titan's Shadow #39)
2 × Quantum Magic (The Mad Titan's Shadow #40)
=== Aggression cards ===
1 × The Power of Aggression (Core Set #55)
1 × Drop Kick (Hulk #14)
1 × Martial Prowess (Hulk #18)
1 × Magic Attack (The Mad Titan's Shadow #43)
=== Justice cards ===
1 × The Power of Justice (Core Set #62)
1 × Concussive Blow (Ms. Marvel #31)
1 × "Think Fast!" (Drax #31)
1 × Zone of Silence (The Mad Titan's Shadow #50)
=== Leadership cards ===
1 × The Power of Leadership (Core Set #72)
1 × "Welcome Aboard" (Venom #27)
1 × Kaluu (The Mad Titan's Shadow #14)
1 × Summoning Spell (The Mad Titan's Shadow #55)
=== Protection cards ===
1 × The Power of Protection (Core Set #79)
1 × Tackle (Ms. Marvel #15)
1 × Brother Voodoo (Doctor Strange #12)
1 × Shield Spell (The Mad Titan's Shadow #61)
=== Basic cards ===
1 × Nick Fury (Core Set #84)
1 × Energy (Core Set #88)
1 × Genius (Core Set #89)
1 × Strength (Core Set #90)
1 × The Sorcerer Supreme (Doctor Strange #26)
1 × The Power in All of Us (Wasp #24)
1 × Spiritual Meditation (Scarlet Witch #19)
1 × Deft Focus (Galaxy's Most Wanted #24)
1 × Gamora (Drax #20)
```
