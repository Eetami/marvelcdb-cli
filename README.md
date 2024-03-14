# MarvelCDB CLI

Command-line interface for viewing decks and decklists.

By default mcdbcli prints the deck in release order grouped by aspect.

## Options

* -d ARG

Print a deck by id

```sh
mcdbcli -d 677339
```

* -l ARG

Print a decklist by id

```sh
mcdbcli -l 36680
```

* -a

  Print aspect in alphabetical order.
  Combining with another -a prints the cards in absolute alphabetical order instead.
  Can be combined with -p and -w options.
* -p

  Print in pack order.
  Can be combined with -a option.
* -r

  Print in absolute release order.
* -w

  Print in wave order.
  Can be combined with -a option.

Without -d or -l arguments `mcdbcli` will read deck as JSON from stdin

```sh
curl -s https://marvelcdb.com/api/public/decklist/36680 | mcdbcli
```

## MarvelCDB API

mcdbcli options only support public APIs. To print your private decks you need to fetch them
using the OAuth API yourself, and feed the JSON to mcdbcli via stdin.

## Example

Print a popular decklist by aspect:

```console
$ mcdbcli -l 13922
Wild Tutor - Adam Warlock
 Adam Warlock cards
  1 × Pip the Troll (Wave #4 The Mad Titan's Shadow #32)
  1 × Soul World (Wave #4 The Mad Titan's Shadow #33)
  1 × Karmic Staff (Wave #4 The Mad Titan's Shadow #34)
  1 × Warlock's Cape (Wave #4 The Mad Titan's Shadow #35)
  2 × Cosmic Ward (Wave #4 The Mad Titan's Shadow #36)
  2 × Mystic Senses (Wave #4 The Mad Titan's Shadow #37)
  3 × Karmic Blast (Wave #4 The Mad Titan's Shadow #38)
  2 × Cosmic Awareness (Wave #4 The Mad Titan's Shadow #39)
  2 × Quantum Magic (Wave #4 The Mad Titan's Shadow #40)
 Aggression cards
  1 × The Power of Aggression (Wave #1 Core Set #55)
  1 × Drop Kick (Wave #1 Hulk #14)
  1 × Martial Prowess (Wave #1 Hulk #18)
  1 × Magic Attack (Wave #4 The Mad Titan's Shadow #43)
 Justice cards
  1 × The Power of Justice (Wave #1 Core Set #62)
  1 × Concussive Blow (Wave #1 Ms. Marvel #31)
  1 × "Think Fast!" (Wave #3 Drax #31)
  1 × Zone of Silence (Wave #4 The Mad Titan's Shadow #50)
 Leadership cards
  1 × The Power of Leadership (Wave #1 Core Set #72)
  1 × "Welcome Aboard" (Wave #3 Venom #27)
  1 × Kaluu (Wave #4 The Mad Titan's Shadow #14)
  1 × Summoning Spell (Wave #4 The Mad Titan's Shadow #55)
 Protection cards
  1 × The Power of Protection (Wave #1 Core Set #79)
  1 × Tackle (Wave #1 Ms. Marvel #15)
  1 × Brother Voodoo (Wave #1 Doctor Strange #12)
  1 × Shield Spell (Wave #4 The Mad Titan's Shadow #61)
 Basic cards
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

Print a popular decklist in waves by aspect:

```console
$ mcdbcli -l 13922 -w
Wild Tutor - Adam Warlock
Wave #1
 Aggression cards
  1 × The Power of Aggression (Wave #1 Core Set #55)
  1 × Drop Kick (Wave #1 Hulk #14)
  1 × Martial Prowess (Wave #1 Hulk #18)
 Justice cards
  1 × The Power of Justice (Wave #1 Core Set #62)
  1 × Concussive Blow (Wave #1 Ms. Marvel #31)
 Leadership cards
  1 × The Power of Leadership (Wave #1 Core Set #72)
 Protection cards
  1 × The Power of Protection (Wave #1 Core Set #79)
  1 × Tackle (Wave #1 Ms. Marvel #15)
  1 × Brother Voodoo (Wave #1 Doctor Strange #12)
 Basic cards
  1 × Nick Fury (Wave #1 Core Set #84)
  1 × Energy (Wave #1 Core Set #88)
  1 × Genius (Wave #1 Core Set #89)
  1 × Strength (Wave #1 Core Set #90)
  1 × The Sorcerer Supreme (Wave #1 Doctor Strange #26)
Wave #2
 Basic cards
  1 × The Power in All of Us (Wave #2 Wasp #24)
  1 × Spiritual Meditation (Wave #2 Scarlet Witch #19)
Wave #3
 Justice cards
  1 × "Think Fast!" (Wave #3 Drax #31)
 Leadership cards
  1 × "Welcome Aboard" (Wave #3 Venom #27)
 Basic cards
  1 × Deft Focus (Wave #3 Galaxy's Most Wanted #24)
  1 × Gamora (Wave #3 Drax #20)
Wave #4
 Adam Warlock cards
  1 × Pip the Troll (Wave #4 The Mad Titan's Shadow #32)
  1 × Soul World (Wave #4 The Mad Titan's Shadow #33)
  1 × Karmic Staff (Wave #4 The Mad Titan's Shadow #34)
  1 × Warlock's Cape (Wave #4 The Mad Titan's Shadow #35)
  2 × Cosmic Ward (Wave #4 The Mad Titan's Shadow #36)
  2 × Mystic Senses (Wave #4 The Mad Titan's Shadow #37)
  3 × Karmic Blast (Wave #4 The Mad Titan's Shadow #38)
  2 × Cosmic Awareness (Wave #4 The Mad Titan's Shadow #39)
  2 × Quantum Magic (Wave #4 The Mad Titan's Shadow #40)
 Aggression cards
  1 × Magic Attack (Wave #4 The Mad Titan's Shadow #43)
 Justice cards
  1 × Zone of Silence (Wave #4 The Mad Titan's Shadow #50)
 Leadership cards
  1 × Kaluu (Wave #4 The Mad Titan's Shadow #14)
  1 × Summoning Spell (Wave #4 The Mad Titan's Shadow #55)
 Protection cards
  1 × Shield Spell (Wave #4 The Mad Titan's Shadow #61)
```

Print a popular deck in packs by aspect:

```console
$ mcdbcli -l 13922 -p
Wild Tutor - Adam Warlock
Core Set
 Aggression cards
  1 × The Power of Aggression (Wave #1 Core Set #55)
 Justice cards
  1 × The Power of Justice (Wave #1 Core Set #62)
 Leadership cards
  1 × The Power of Leadership (Wave #1 Core Set #72)
 Protection cards
  1 × The Power of Protection (Wave #1 Core Set #79)
 Basic cards
  1 × Nick Fury (Wave #1 Core Set #84)
  1 × Energy (Wave #1 Core Set #88)
  1 × Genius (Wave #1 Core Set #89)
  1 × Strength (Wave #1 Core Set #90)
Ms. Marvel
 Justice cards
  1 × Concussive Blow (Wave #1 Ms. Marvel #31)
 Protection cards
  1 × Tackle (Wave #1 Ms. Marvel #15)
Doctor Strange
 Protection cards
  1 × Brother Voodoo (Wave #1 Doctor Strange #12)
 Basic cards
  1 × The Sorcerer Supreme (Wave #1 Doctor Strange #26)
Hulk
 Aggression cards
  1 × Drop Kick (Wave #1 Hulk #14)
  1 × Martial Prowess (Wave #1 Hulk #18)
Wasp
 Basic cards
  1 × The Power in All of Us (Wave #2 Wasp #24)
Scarlet Witch
 Basic cards
  1 × Spiritual Meditation (Wave #2 Scarlet Witch #19)
Galaxy's Most Wanted
 Basic cards
  1 × Deft Focus (Wave #3 Galaxy's Most Wanted #24)
Drax
 Justice cards
  1 × "Think Fast!" (Wave #3 Drax #31)
 Basic cards
  1 × Gamora (Wave #3 Drax #20)
Venom
 Leadership cards
  1 × "Welcome Aboard" (Wave #3 Venom #27)
The Mad Titan's Shadow
 Adam Warlock cards
  1 × Pip the Troll (Wave #4 The Mad Titan's Shadow #32)
  1 × Soul World (Wave #4 The Mad Titan's Shadow #33)
  1 × Karmic Staff (Wave #4 The Mad Titan's Shadow #34)
  1 × Warlock's Cape (Wave #4 The Mad Titan's Shadow #35)
  2 × Cosmic Ward (Wave #4 The Mad Titan's Shadow #36)
  2 × Mystic Senses (Wave #4 The Mad Titan's Shadow #37)
  3 × Karmic Blast (Wave #4 The Mad Titan's Shadow #38)
  2 × Cosmic Awareness (Wave #4 The Mad Titan's Shadow #39)
  2 × Quantum Magic (Wave #4 The Mad Titan's Shadow #40)
 Aggression cards
  1 × Magic Attack (Wave #4 The Mad Titan's Shadow #43)
 Justice cards
  1 × Zone of Silence (Wave #4 The Mad Titan's Shadow #50)
 Leadership cards
  1 × Kaluu (Wave #4 The Mad Titan's Shadow #14)
  1 × Summoning Spell (Wave #4 The Mad Titan's Shadow #55)
 Protection cards
  1 × Shield Spell (Wave #4 The Mad Titan's Shadow #61)
```

Print a popular deck in alphabetical order by aspect:

```console
$ mcdbcli -l 13922 -a
Wild Tutor - Adam Warlock
 Adam Warlock cards
  2 × Cosmic Awareness (Wave #4 The Mad Titan's Shadow #39)
  2 × Cosmic Ward (Wave #4 The Mad Titan's Shadow #36)
  3 × Karmic Blast (Wave #4 The Mad Titan's Shadow #38)
  1 × Karmic Staff (Wave #4 The Mad Titan's Shadow #34)
  2 × Mystic Senses (Wave #4 The Mad Titan's Shadow #37)
  1 × Pip the Troll (Wave #4 The Mad Titan's Shadow #32)
  2 × Quantum Magic (Wave #4 The Mad Titan's Shadow #40)
  1 × Soul World (Wave #4 The Mad Titan's Shadow #33)
  1 × Warlock's Cape (Wave #4 The Mad Titan's Shadow #35)
 Aggression cards
  1 × Drop Kick (Wave #1 Hulk #14)
  1 × Magic Attack (Wave #4 The Mad Titan's Shadow #43)
  1 × Martial Prowess (Wave #1 Hulk #18)
  1 × The Power of Aggression (Wave #1 Core Set #55)
 Justice cards
  1 × "Think Fast!" (Wave #3 Drax #31)
  1 × Concussive Blow (Wave #1 Ms. Marvel #31)
  1 × The Power of Justice (Wave #1 Core Set #62)
  1 × Zone of Silence (Wave #4 The Mad Titan's Shadow #50)
 Leadership cards
  1 × "Welcome Aboard" (Wave #3 Venom #27)
  1 × Kaluu (Wave #4 The Mad Titan's Shadow #14)
  1 × Summoning Spell (Wave #4 The Mad Titan's Shadow #55)
  1 × The Power of Leadership (Wave #1 Core Set #72)
 Protection cards
  1 × Brother Voodoo (Wave #1 Doctor Strange #12)
  1 × Shield Spell (Wave #4 The Mad Titan's Shadow #61)
  1 × Tackle (Wave #1 Ms. Marvel #15)
  1 × The Power of Protection (Wave #1 Core Set #79)
 Basic cards
  1 × Deft Focus (Wave #3 Galaxy's Most Wanted #24)
  1 × Energy (Wave #1 Core Set #88)
  1 × Gamora (Wave #3 Drax #20)
  1 × Genius (Wave #1 Core Set #89)
  1 × Nick Fury (Wave #1 Core Set #84)
  1 × Spiritual Meditation (Wave #2 Scarlet Witch #19)
  1 × Strength (Wave #1 Core Set #90)
  1 × The Power in All of Us (Wave #2 Wasp #24)
  1 × The Sorcerer Supreme (Wave #1 Doctor Strange #26)
```

Print a popular deck in waves in alphabetical order by aspect:

```console
$ mcdbcli -l 13922 -a -w
Wild Tutor - Adam Warlock
Wave #1
 Aggression cards
  1 × Drop Kick (Wave #1 Hulk #14)
  1 × Martial Prowess (Wave #1 Hulk #18)
  1 × The Power of Aggression (Wave #1 Core Set #55)
 Justice cards
  1 × Concussive Blow (Wave #1 Ms. Marvel #31)
  1 × The Power of Justice (Wave #1 Core Set #62)
 Leadership cards
  1 × The Power of Leadership (Wave #1 Core Set #72)
 Protection cards
  1 × Brother Voodoo (Wave #1 Doctor Strange #12)
  1 × Tackle (Wave #1 Ms. Marvel #15)
  1 × The Power of Protection (Wave #1 Core Set #79)
 Basic cards
  1 × Energy (Wave #1 Core Set #88)
  1 × Genius (Wave #1 Core Set #89)
  1 × Nick Fury (Wave #1 Core Set #84)
  1 × Strength (Wave #1 Core Set #90)
  1 × The Sorcerer Supreme (Wave #1 Doctor Strange #26)
Wave #2
 Basic cards
  1 × Spiritual Meditation (Wave #2 Scarlet Witch #19)
  1 × The Power in All of Us (Wave #2 Wasp #24)
Wave #3
 Justice cards
  1 × "Think Fast!" (Wave #3 Drax #31)
 Leadership cards
  1 × "Welcome Aboard" (Wave #3 Venom #27)
 Basic cards
  1 × Deft Focus (Wave #3 Galaxy's Most Wanted #24)
  1 × Gamora (Wave #3 Drax #20)
Wave #4
 Adam Warlock cards
  2 × Cosmic Awareness (Wave #4 The Mad Titan's Shadow #39)
  2 × Cosmic Ward (Wave #4 The Mad Titan's Shadow #36)
  3 × Karmic Blast (Wave #4 The Mad Titan's Shadow #38)
  1 × Karmic Staff (Wave #4 The Mad Titan's Shadow #34)
  2 × Mystic Senses (Wave #4 The Mad Titan's Shadow #37)
  1 × Pip the Troll (Wave #4 The Mad Titan's Shadow #32)
  2 × Quantum Magic (Wave #4 The Mad Titan's Shadow #40)
  1 × Soul World (Wave #4 The Mad Titan's Shadow #33)
  1 × Warlock's Cape (Wave #4 The Mad Titan's Shadow #35)
 Aggression cards
  1 × Magic Attack (Wave #4 The Mad Titan's Shadow #43)
 Justice cards
  1 × Zone of Silence (Wave #4 The Mad Titan's Shadow #50)
 Leadership cards
  1 × Kaluu (Wave #4 The Mad Titan's Shadow #14)
  1 × Summoning Spell (Wave #4 The Mad Titan's Shadow #55)
 Protection cards
  1 × Shield Spell (Wave #4 The Mad Titan's Shadow #61)
```

Print a popular deck in absolute release order:

```console
$ mcdbcli -l 13922 -r
Wild Tutor - Adam Warlock
  1 × The Power of Aggression (Wave #1 Core Set #55)
  1 × The Power of Justice (Wave #1 Core Set #62)
  1 × The Power of Leadership (Wave #1 Core Set #72)
  1 × The Power of Protection (Wave #1 Core Set #79)
  1 × Nick Fury (Wave #1 Core Set #84)
  1 × Energy (Wave #1 Core Set #88)
  1 × Genius (Wave #1 Core Set #89)
  1 × Strength (Wave #1 Core Set #90)
  1 × Tackle (Wave #1 Ms. Marvel #15)
  1 × Concussive Blow (Wave #1 Ms. Marvel #31)
  1 × Brother Voodoo (Wave #1 Doctor Strange #12)
  1 × The Sorcerer Supreme (Wave #1 Doctor Strange #26)
  1 × Drop Kick (Wave #1 Hulk #14)
  1 × Martial Prowess (Wave #1 Hulk #18)
  1 × The Power in All of Us (Wave #2 Wasp #24)
  1 × Spiritual Meditation (Wave #2 Scarlet Witch #19)
  1 × Deft Focus (Wave #3 Galaxy's Most Wanted #24)
  1 × Gamora (Wave #3 Drax #20)
  1 × "Think Fast!" (Wave #3 Drax #31)
  1 × "Welcome Aboard" (Wave #3 Venom #27)
  1 × Kaluu (Wave #4 The Mad Titan's Shadow #14)
  1 × Pip the Troll (Wave #4 The Mad Titan's Shadow #32)
  1 × Soul World (Wave #4 The Mad Titan's Shadow #33)
  1 × Karmic Staff (Wave #4 The Mad Titan's Shadow #34)
  1 × Warlock's Cape (Wave #4 The Mad Titan's Shadow #35)
  2 × Cosmic Ward (Wave #4 The Mad Titan's Shadow #36)
  2 × Mystic Senses (Wave #4 The Mad Titan's Shadow #37)
  3 × Karmic Blast (Wave #4 The Mad Titan's Shadow #38)
  2 × Cosmic Awareness (Wave #4 The Mad Titan's Shadow #39)
  2 × Quantum Magic (Wave #4 The Mad Titan's Shadow #40)
  1 × Magic Attack (Wave #4 The Mad Titan's Shadow #43)
  1 × Zone of Silence (Wave #4 The Mad Titan's Shadow #50)
  1 × Summoning Spell (Wave #4 The Mad Titan's Shadow #55)
  1 × Shield Spell (Wave #4 The Mad Titan's Shadow #61)
```

Print a popular deck in absolute alphabetical order (you madman!):

```console
$ mcdbcli -l 13922 -aa
Wild Tutor - Adam Warlock
  1 × "Think Fast!" (Wave #3 Drax #31)
  1 × "Welcome Aboard" (Wave #3 Venom #27)
  1 × Brother Voodoo (Wave #1 Doctor Strange #12)
  1 × Concussive Blow (Wave #1 Ms. Marvel #31)
  2 × Cosmic Awareness (Wave #4 The Mad Titan's Shadow #39)
  2 × Cosmic Ward (Wave #4 The Mad Titan's Shadow #36)
  1 × Deft Focus (Wave #3 Galaxy's Most Wanted #24)
  1 × Drop Kick (Wave #1 Hulk #14)
  1 × Energy (Wave #1 Core Set #88)
  1 × Gamora (Wave #3 Drax #20)
  1 × Genius (Wave #1 Core Set #89)
  1 × Kaluu (Wave #4 The Mad Titan's Shadow #14)
  3 × Karmic Blast (Wave #4 The Mad Titan's Shadow #38)
  1 × Karmic Staff (Wave #4 The Mad Titan's Shadow #34)
  1 × Magic Attack (Wave #4 The Mad Titan's Shadow #43)
  1 × Martial Prowess (Wave #1 Hulk #18)
  2 × Mystic Senses (Wave #4 The Mad Titan's Shadow #37)
  1 × Nick Fury (Wave #1 Core Set #84)
  1 × Pip the Troll (Wave #4 The Mad Titan's Shadow #32)
  2 × Quantum Magic (Wave #4 The Mad Titan's Shadow #40)
  1 × Shield Spell (Wave #4 The Mad Titan's Shadow #61)
  1 × Soul World (Wave #4 The Mad Titan's Shadow #33)
  1 × Spiritual Meditation (Wave #2 Scarlet Witch #19)
  1 × Strength (Wave #1 Core Set #90)
  1 × Summoning Spell (Wave #4 The Mad Titan's Shadow #55)
  1 × Tackle (Wave #1 Ms. Marvel #15)
  1 × The Power in All of Us (Wave #2 Wasp #24)
  1 × The Power of Aggression (Wave #1 Core Set #55)
  1 × The Power of Justice (Wave #1 Core Set #62)
  1 × The Power of Leadership (Wave #1 Core Set #72)
  1 × The Power of Protection (Wave #1 Core Set #79)
  1 × The Sorcerer Supreme (Wave #1 Doctor Strange #26)
  1 × Warlock's Cape (Wave #4 The Mad Titan's Shadow #35)
  1 × Zone of Silence (Wave #4 The Mad Titan's Shadow #50)
```

## Caching

mcdbcli caches the loaded cards to your home directory under `~/.mcdb/cards`. To remove the cached cards run the following command

```sh
rm -rf ~/.mcdb
```
