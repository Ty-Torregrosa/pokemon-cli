# pokemon-cli
## Description
This is a simple CLI using the RESTful Pokemon API.


## Requirements
The user should be able to:
1. Look up Pokemon by name, print out moves (alphabetical order).
2. Look up Pokemon by pokedex number, print out moves (alphabetical order).
3. Look up moves by type, print top 10 most moves.
4. The CLI should support an optional generation; as well.
If provided, the CLI will filter on moves/pokemon available in the version flag ONLY.
5. Errors should be handled gracefully, with appropriate messages to the user.

## Known Bugs

The --generation flag works correctly when following the --lookup flag.
It uses the game version name (exact match only).
It cannot actually take a generation name.
--generation is an exact match, user cannot specify gold or silver and match the generation gold-silver
When --generation is combined with the --move-type flag, the user will need to use the generation name, not the game version name. example: pokemon --move-type fire --generation yellow fails, pokemon --move-type fire --generation generation-i succeeds 

## Possible Improvements

Top 10 moves currently defaults to 10 moves with lowest move id.
They are the same no matter what generation specified (despite some hard work to implement checking)

Add suggestions for inputs that are close to a value.
For instance pika tries to autocomplete to pikachu.

Restructuring cli to have subcommands + flags
Example:
pokemon lookup pikachu --generation yellow

Additional flags for narrowing down move type
Additional flags for full subset of information

Any of these additional features would open conversation for code restructuring.
Each might have their own function with some sort of case statement redirecting execution to each one.
The current conditionals based on parameter instantion are crude at best.
Restructing the cli as previously described would more easily allow for this improvement,
as well as allow developers to more fully take advantage of the python Click module.  

