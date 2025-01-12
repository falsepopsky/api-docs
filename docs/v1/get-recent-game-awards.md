<script setup>
import SampleRequest from '../components/SampleRequest.vue';
</script>

# All Recent Game Awards

A call to this endpoint will retrieve all recently granted game awards across the site's userbase.

[[toc]]

## On-site Representation

This data can be found on the Recent Game Awards page, for example:

![Recent Game Awards](/recent-game-awards.png)

## HTTP Request

<SampleRequest httpVerb="GET">https://retroachievements.org/API/API_GetRecentGameAwards.php</SampleRequest>

### Query Parameters

| Name | Required? | Description                                                                                                                                                                |
| :--- | :-------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `z`  | Yes       | Your username.                                                                                                                                                             |
| `y`  | Yes       | Your web API key.                                                                                                                                                          |
| `d`  |           | Starting date (YYYY-MM-DD) (default: now).                                                                                                                                 |
| `o`  |           | Offset, number of entries to skip (default: 0).                                                                                                                            |
| `c`  |           | Count, number of entries to return (default: 25, maximum: 100).                                                                                                            |
| `k`  |           | A comma-separated list of desired game award kinds. Possible values are "beaten-softcore", "beaten-hardcore", "completed", and "mastered" (default: all game award kinds). |

## Client Library

Not yet supported.

## Response

::: code-group

```json [HTTP Response]
{
  "Count": 25,
  "Total": 172318,
  "Results": [
    {
      "User": "renanbrj",
      "AwardKind": "mastered",
      "AwardDate": "2022-01-01T23:48:04+00:00",
      "GameID": 14284,
      "GameTitle": "Batman Returns",
      "ConsoleID": 15,
      "ConsoleName": "Game Gear"
    }
    // ...
  ]
}
```

:::

## Source

| Repo  | URL                                                                                           |
| :---- | :-------------------------------------------------------------------------------------------- |
| RAWeb | https://github.com/RetroAchievements/RAWeb/blob/master/public/API/API_GetRecentGameAwards.php |
