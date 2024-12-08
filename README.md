# Some example queries

## Retrieve all game copies and associated game names with condition "good"

```graphql
query {
	allGameCopies(filter: {
    condition: "good"
  }) {
    id,
    BoardGame {
      name
    }
  }
}
```

## Add a game copy for Cute Cats Puzzle

### Step 1: determine id of Cute Cats Puzzle game

```graphql
query {
  allBoardGames(filter: {
    name: "Cute Cats Puzzle"
  }) {
    id
  }
}
```

Outcome: "5"

### Step 2: add a game copy

```graphql
mutation {
  createGameCopy(boardGame_id: 5, condition: "good") {
    id
  }
}
```