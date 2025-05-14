# Play 2048 on Monad

**Check out a full writeup of how we built this [here](https://blog.monad.xyz/blog/build-2048).**

Smart contracts that let you play a game of 2048 entirely on-chain. The game is deployed on [Monad testnet](https://testnet.monad.xyz/) to showcase how Monad is well suited for building fast paced games with a high volume of interactions.

### About the game

From the [2048 Wikipedia](<https://en.wikipedia.org/wiki/2048_(video_game)>) page:

-   2048 is a single-player sliding tile puzzle video game.
-   2048 is played on a plain 4×4 grid, with numbered tiles that slide when a player moves them using the four arrow keys.
-   The game begins with two tiles already in the grid, having a value of either 2 or 4, and another such tile appears in a random empty space after each turn. - Tiles with a value of 2 appear 90% of the time, and tiles with a value of 4 appear 10% of the time.
-   Tiles slide as far as possible in the chosen direction until they are stopped by either another tile or the edge of the grid. If two tiles of the same number collide while moving, they will merge into a tile with the total value of the two tiles that collided.
-   The resulting tile cannot merge with another tile again in the same move.

## Deployments

`Monad2048.sol` is deployed on Monad testnet: [0xe0FA8195AE92b9C473c0c0c12c2D6bCbd245De47](https://testnet.monadexplorer.com/address/0xe0FA8195AE92b9C473c0c0c12c2D6bCbd245De47).

## Development

This is a Foundry project. You can find installation instructions for foundry, [here](https://book.getfoundry.sh/getting-started/installation). Clone the repository and run the following commands:

### Install

```shell
$ forge install
```

### Build

```shell
$ forge build
```

### Test

```shell
$ forge test
```

### Format

```shell
$ forge fmt
```

## Documentation

The `Monad2048.sol` smart contract contains the API to play a game of 2048.

-   `startGame`: Starts a new game of 2048 for a player (`msg.sender`). The player reveals and reserves the first 4 boards of the game and the contract validates that this is a legal game of 2048.
-   `play`: Lets a player make a move for a game by providing the game's session ID and the result board or applying a move (UP, DOWN, LEFT or RIGHT) on the latest board of the game. The contract then validates that the player has made a valid move (board transformation).

The `LiBoard` library implements the logic of board transformations, and other helper functions for extracting information about a given board position.

The contract has no permissions or privileged actors.

## Feedback

Please open issues or PRs on this repositories for any feedback.
