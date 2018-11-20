# Dagron

## Information

*CTF*: Hungry Hungry Hackers 2017

*Category*: Re

*Point Value*: Can't Remember. 100?

*Writeup Author*: github.com/helithumper

## Summary / Situation

```
We were given an ELF binary and told to look for a flag.
```

When you run the ELF, the following text appears:

```
                                  /   \
 _                        )      ((   ))     (
(@)                      /|\      ))_((     /|\
|-|                     / | \    (/\|/\)   / | \                      (@)
| | -------------------/--|-voV---\`|'/--Vov-|--\---------------------|-|
|-|                         '^`   (o o)  '^`                          | |
| |                               `\Y/'                               |-|
|-|                                                                   | |
| |                Welcome to Hungry Hungry Dragons!                  |-|
|-|                                                                   | |
| |                                                                   |-|
|_|___________________________________________________________________| |
(@)              l   /\ /         ( (       \ /\   l                `\|-|
                 l /   V           \ \       V   \ l                  (@)
                 l/                _) )_          \I
                                   `\ /'
```

So my first idea was to run `strings` on the file. When looking through the output of `strings` the following line popped up:

`flag{31b9307b77418383}`

So after a bit of looking back, I was wondering why the flag was in strings. Where in the file was it? So I opened up the binary in Binary Ninja and found a function called `display_flag` and the function appears to just `puts` the flag.