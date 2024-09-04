# graphql-games-project

Following tutorial https://www.youtube.com/watch?v=5199E50O7SI

## Steps
1. Install dependency `npm install @apollo/server graphql`
2. Run project on port `localhost:4000` by running `node index`

## Sample Queries

### GamesQuery
```
query GamesQuery {
  games {
    title,
    platform,
  }
}
```
### ReviewQuery
```
query ReviewQuery($id: ID!) {
  review(id: $id) {
    rating,
    content
  }
}
```
Variables:
```
{
  "id": "1"
}
```

### GameQuery
```
query GameQuery($id: ID!) {
  game(id: $id) {
    title,
    platform,
    id,
    reviews {
      rating,
      content
    }
  }
}
```
Variables:
```
{
  "id": "2"
}
```

### DeleteMutation
```
mutation DeleteMutation($id: ID!) {
  deleteGame(id: $id) {
    id,
    title,
    platform
  }
}
```
Variables:
```
{
  "id": "2"
}
```

### AddGame
```
mutation AddGame($game: AddGameInput!) {
  addGame(game: $game) {
    id,
    title,
    platform
  }
}
```
Variables:
```
{
  "game": {
    "title": "a new game",
    "platform": ["switch", "ps5"]
  }
}
```

### EditGame
```
mutation EditGame($id: ID!, $edits: EditGameInput!) {
  updateGame(id: $id, edits: $edits) {
    title,
    platform
  }
}
```
Variables:
```
{
  "edits": {
    "title": "dark souls"
  },
  "id": "2"
}
```
