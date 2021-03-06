* [kayn Methods](#methods)
* [Endpoints](#endpoints)

# Methods 

```javascript
/* CHAMPION-MASTERY-V3 */
ChampionMastery.list(summonerID: int)
ChampionMastery.get(summonerID: int)(championID: int)
ChampionMastery.totalScore(summonerID: int)
/* CHAMPION-MASTERY-V4 */
ChampionMasteryV4.list(summonerID: string)
ChampionMasteryV4.get(summonerID: string)(championID: int)
ChampionMasteryV4.totalScore(summonerID: string)

/* CHAMPION-V3 */
Champion.Rotation.list()

/* LEAGUE-V3 */
Challenger.list(queueName: string)
League.by.uuid(leagueUUID: string)
Master.list(queueName: string)
LeaguePositions.by.summonerID(summonerID: int)
/* LEAGUE-V4 */
ChallengerV4.list(queueName: string)
LeagueV4.by.uuid(leagueUUID: string)
MasterV4.list(queueName: string)
LeaguePositionsV4.by.summonerID(summonerID: string)

/* DDRAGON
    At its core, DDragonRequest uses `version()` and `locale()`.

    DDragonRequest as of v0.8.22 now also uses `region()` to automatically grab the correct version for the current request (only for data requests like champion lists). DDragonRequest does not use `query()`.

    Both `version()` and `locale()` are optional.
*/
DDragon.Champion.get(championName: string)
DDragon.Champion.list()
DDragon.Champion.listFull()

DDragon.Champion.getDataById(championName: string)
DDragon.Champion.getDataByIdWithParentAsId(championName: string)
DDragon.Champion.listDataById()
DDragon.Champion.listDataByIdWithParentAsId()
DDragon.Champion.listFullDataById()
DDragon.Champion.listFullDataByIdWithParentAsId()

DDragon.Item.list()
DDragon.Language.list()
DDragon.LanguageString.list()
DDragon.Map.list()
DDragon.ProfileIcon.list()
DDragon.Realm.list(region: region)
DDragon.RunesReforged.list()
DDragon.SummonerSpell.list()
DDragon.Version.list()

/* LOL-STATUS-V3 */
Status.get()

/* MATCH-V3 */
Match.get(matchID: int)
Matchlist.by.accountID(accountID: int)
Matchlist.Recent.by.accountID(accountID: int) /* April 27th deprecation by Riot, but will still work via the above endpoint */
Match.timeline(matchID: int)
Match.Tournament.listMatchIDs(tournamentCode: string)
Match.Tournament.get(matchID: int, tournamentCode: string)
/* MATCH-V4 */
MatchV4.get(matchID: string)
MatchlistV4.by.accountID(accountID: string)
MatchlistV4.Recent.by.accountID(accountID: string) /* April 27th deprecation by Riot, but will still work via the above endpoint */
MatchV4.timeline(matchID: int)

/* SPECTATOR-V3 */
CurrentGame.by.summonerID(summonerID: int)
FeaturedGames.list()
/* SPECTATOR-V4 */
CurrentGameV4.by.summonerID(summonerID: string)
FeaturedGamesV4.list()

/* SUMMONER-V3 */
Summoner.by.name(summonerName: string)
Summoner.by.id(summonerID: int)
Summoner.by.accountID(accountID: int)
/* SUMMONER-V4 */
SummonerV4.by.name(summonerName: string)
SummonerV4.by.id(summonerID: string)
SummonerV4.by.accountID(accountID: string)

/* THIRD-PARTY-CODE-V3 */
ThirdPartyCode.by.summonerID(summonerID: int)
/* THIRD-PARTY-CODE-V4 */
ThirdPartyCodeV4.by.summonerID(summonerID: string)

/* TOURNAMENT-STUB-V3 */
TournamentStub.create(tournamentID: number, body: object?)
TournamentStub.lobbyEvents(tournamentCode: string)
TournamentStub.registerProviderData(region: string, callbackURL: string)
TournamentStub.register(providerID: number, name: string?)

/* TOURNAMENT-V3 */
Tournament.create(tournamentID: number, body: object?)
Tournament.update(tournamentCode: string, body: object)
Tournament.get(tournamentCode: string)
Tournament.lobbyEvents(tournamentCode: string)
Tournament.registerProviderData(region: string, callbackURL: string)
TournamentStub.register(providerID: number, name: string?)
```

# Endpoints 

Everything should be in the same order as in the official docs.

## CHAMPION-MASTERY-V3
- [x] `Get all champion mastery entries sorted by number of champion points descending,`
- [x] `Get a champion mastery by player ID and champion ID.`
- [x] `Get a player's total champion mastery score, which is the sum of individual champion mastery levels.`

## CHAMPION-V3
- [x] `Retrieve all champions.`
- [x] `Retrieve champion by ID.`

## LEAGUE-V3
- [x] - `Get the challenger league for given queue.`
- [x] - `Get league with given ID, including inactive entries.`
- [x] - `Get the master league for given queue.`
- [x] - `Get league positions in all queues for given summoner ID.`

## LOL-STATUS-V3
- [x] - `Get League of Legends status for the given shard.`

## MATCH-V3
- [x] - `Get match by match ID.`
- [x] - `Get matchlist for games played on given account ID and platform ID and filtered using given filter parameters, if any.`
- [x] - `Get matchlist for last 20 matches played on given account ID and platform ID.` (implemented via Get matchlist)
- [x] - `Get match timeline by match ID.`
- [x] - `Get match IDs by tournament code.`
- [x] - `Get match by match ID and tournament code.`

## SPECTATOR-V3
- [x] - `Get current game information for the given summoner ID.`
- [x] - `Get list of featured games.`

## SUMMONER-V3
- [x] - `Get a summoner by account ID.`
- [x] - `Get a summoner by summoner name.`
- [x] - `Get a summoner by summoner ID.`

## TOURNAMENT-STUB-V3
- [x] - `Create a mock tournament code for the given tournament.`
- [x] - `Gets a mock list of lobby events by tournament code.`
- [x] - `Creates a mock tournament provider and return its ID.`
- [x] - `Creates a mock tournament and return its ID.`

## TOURNAMENT-V3
- [x] - `Create a tournament code for the given tournament.`
- [x] - `Update the pick type, map, spectator type, or allowed summoners for a code.`
- [x] - `Returns the tournament code DTO associated with a tournament code string.`
- [x] - `Gets a list of lobby events by tournament code.`
- [x] - `Creates a tournament provider and return its ID.`
- [x] - `Creates a tournament and return its ID.`
