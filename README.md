# esiJS

esiJS is a updated module for the EVE Online ESI. It makes getting data from the ESI much easier and results in cleaner code. 

# INSTALLING:
```bash
npm i --save esijs
```

# USAGE:

```js
let esiJS = require('esiJS')
// Use all functions like this:
let a = await esiJS.group.<subgroup>.function() // `<subgroup>` is used in groups like `market` 
                                                // (esiJS.market.groups.groups()) and `universe` 
                                                // (esiJS.universe.ancestries.ancestries())
            .catch(function(e) {
                // whatever you want to do with errors
            })
// functions MUST be 'await'ed, otherwise they wont work properly, except the `util` functions,
// as those are synchronous functions (but can be used as async if you wish)
```

Example usage is also in [EveShopper](https://github.com/GingkathFox/EveShopper).

```js
// ALLIANCE:
await esiJS.alliance.alliances() // returns a array of active alliances
await esiJS.alliance.corps(allianceID) // returns a array of corporations within a alliance
await esiJS.alliance.icon(allianceID) // returns links to the alliance icon
await esiJS.alliance.info(allianceID) // returns info on a alliance

// CHARACTER:
await esiJS.character.affiliation(characterIDArray) // returns a array of corps and alliances a character has been in
await esiJS.character.corpHistory(characterID) // returns a array of all the corporations the character has been in
await esiJS.character.portrait(characterID) // returns links to the characters portrait
await esiJS.character.publicInfo(characterID) // returns all public information about a character

// CONTRACTS (PUBLIC):
await esiJS.contracts.public.contracts(regionID) // returns all active contracts in a region
await esiJS.contracts.public.bids(contractID) // returns all bids on a auction contract
await esiJS.contracts.public.items(contractID) // returns all items in a Item Exchange or Auction contract

// CORPORATION:
await esiJS.corporation.npcCorps() // returns all NPC corporations
await esiJS.corporation.info(corporationID) // returns the info of a corporation
await esiJS.corporation.icons(corporationID) // returns links to the corporation icon
await esiJS.corporation.allianceHistory(corporationID) // returns array of alliances this corporation has been in

// DOGMA:
await esiJS.dogma.attrs() // returns all attributes in game
await esiJS.dogma.attrInfo(attributeID) // returns info on a attribute
await esiJS.dogma.dynItemInfo(itemID, typeID) // returns info on a dynamic item (eg. a railgun with a mutaplasmid)
await esiJS.dogma.effects() // returns all effects in game
await esiJS.dogma.effectInfo(effectID) // returns info on a effect

// FACTION WARFARE:
await esiJS.fw.stats() // returns statistics on factions in faction warfare
await esiJS.fw.systems() // returns systems claimed by faction warfare
await esiJS.fw.wars() // returns data on which NPC factions are at war

// FACTION WARFARE (LEADERBOARDS):
await esiJS.fw.lbs.chars() // returns top pilots in faction warfare
await esiJS.fw.lbs.corps() // returns top corps in faction warfare
await esiJS.fw.lbs.leaderboard() // returns top 4 factions in faction warfare

// INCURSIONS:
await esiJS.incursions.incursions() // returns all current incursions

// INDUSTRY:
await esiJS.industry.facilities() // returns a array of industry facilities
await esiJS.industry.systems() // returns cost indices for all systems

// INSURANCE: 
await esiJS.insurance.prices() // returns available insurance levels for all ship types

// KILLMAILS: 
await esiJS.killmails.getkillMail(killmailID, killmailHash) // returns info on a killmail

// LOYALTY:
await esiJS.loyalty.offers(corporationID) // returns a list of offers from a corporations loyalty store

// MARKET:
await esiJS.market.history(regionID, typeID) // returns a history of prices for a item in a region
await esiJS.market.orders(regionID, pageNumber, buyOrSellOrAll, typeID) // returns orders for a item in a region (typeID is optional)
                                                                  // buyOrSellOrAll defaults to 'all', possible values are
                                                                  // 'buy', 'sell', or 'all'
await esiJS.market.prices() // returns average price and adjusted price of items
await esiJS.market.types(regionID) // returns all item types that have orders in a region

// MARKET(GROUPS):
await esiJS.market.groups.groups() // returns all market groups
await esiJS.market.groups.groupInfo(marketGroupID) // returns info on a market group

// OPPORTUNITIES:
await esiJS.opportunities.groups() // returns all opportunity groups
await esiJS.opportunities.groupInfo(opportunityGroupID) // returns info on a opportunity group
await esiJS.opportunities.tasks() // returns all opportunity tasks
await esiJS.opportunities.taskInfo(opportunityTaskID) // returns info on a opportunity task

// PLANETARY INTERACTION:
await esiJS.pi.schematicInfo(schematicID) // returns info on a planetaty factory schematic

// ROUTES:
await esiJS.routes.planRoute(orginSystemID, destinationSystemID, flag, avoid) // returns route from orgin to destination
                                                                        // flag defaults to 'secure', possible values are
                                                                        // 'shortest', 'secure', and 'insecure'
                                                                        // avoid is a optional array of system IDs

// SEARCH:
await esiJS.search.search(query, category, strict) // searches on a string
                                             // category can be one of the following: 
                                             // 'agent', 'alliance', 'character', 'constellation', 'corporation', 'faction',
                                             // 'inventory_type', 'region', 'solar_system', or 'station'

// SOVEREIGNTY:
await esiJS.sov.campaigns() // returns all sovereignty campaigns
await esiJS.sov.map() // returns sovereignty of all systems
await esiJS.sov.structures() // returns sovereignty of structures

// STATUS:
await esiJS.status.status() // returns status of the server set using 'setSettings()'

// UNIVERSE (ANCESTRIES):
await esiJS.universe.ancestries.ancestries() // returns all character ancestries

// UNIVERSE (BELTS):
await esiJS.universe.belts.beltInfo(beltID) // returns info on a asteriod belt

// UNIVERSE (BLOODLINES):
await esiJS.universe.bloodlines.bloodlines() // returns all character bloodlines

// UNIVERSE (BULK):
await esiJS.universe.bulk.idsToNames(array) // returns names of all ids in the array passed. supported IDs fall into these categories:
                                      // Characters, Corporations, Alliances, Stations, Solar Systems, Constellations, 
                                      // Regions, Types, and Factions 

await esiJS.universe.bulk.namesToIds(array) // returns ids of all names passed that are a exact match in these categories:
                                      // agents, alliances, characters, constellations, corporations, factions, 
                                      // inventory_types, regions, stations, and systems

// UNIVERSE (CATEGORIES):
await esiJS.universe.categories.categories() // returns all categories
await esiJS.universe.categories.categoryInfo(categoryID) // returns info on a category

// UNIVERSE (CONSTELLATIONS):
await esiJS.universe.constellations.constellations() // returns all constellations
await esiJS.universe.constellations.constellationInfo(constellationID) // returns info on a constellation

// UNIVERSE (FACTIONS): 
await esiJS.universe.factions.factions() // returns all factions

// UNIVERSE (GRAPHICS):
await esiJS.universe.graphics.graphics() // returns all graphics
await esiJS.universe.graphics.graphicInfo(graphicID) // returns info on a graphic

// UNIVERSE (GROUPS):
await esiJS.universe.groups.groups() // returns all groups
await esiJS.universe.groups.groupInfo(groupID) // returns info on a group

// UNIVERSE (MOONS):
await esiJS.universe.moons.moonInfo(moonID) // returns info on a moon

// UNIVERSE (PLANETS):
await esiJS.universe.planets.planetInfo(planetID) // returns info on a planet

// UNIVERSE (RACES):
await esiJS.universe.races.races() // returns all character races

// UNIVERSE (REGIONS):
await esiJS.universe.regions.regions() // returns all regions
await esiJS.universe.regions.regionInfo(regionID) // returns info on a region

// UNIVERSE (STARGATES):
await esiJS.universe.stargates.stargateInfo(stargateID) // returns info on a stargate

// UNIVERSE (STARS):
await esiJS.universe.stars.starInfo(starID) // returns info on a star

// UNIVERSE (STATIONS):
await esiJS.universe.stations.stationInfo(stationID) // returns info on a station

// UNIVERSE (STRUCTURES):
await esiJS.universe.structures.structures() // returns all structures

// UNIVERSE (SYSTEMS):
await esiJS.universe.systems.systems() // returns all systems
await esiJS.universe.systems.systemInfo(systemID) // returns info on a system
await esiJS.universe.systems.systemKills() // returns all system kills within the last hour, excluding wormhole space
await esiJS.universe.systems.systemJumps() // returns the jumps into a system within the last hour

// UNIVERSE (TYPES):
await esiJS.universe.types.types() // returns all types
await esiJS.universe.types.typeInfo(typeID) // returns info on a type

// WARS:
await esiJS.wars.wars() // returns a list of wars
await esiJS.wars.warInfo(warID) // returns info on a war
await esiJS.wars.warKills(warID) // returns all kills in a war

// UTILITY:
esiJS.util.getSettings() // returns the current settings
esiJS.util.setSettings(route, dataSource) // sets the route taken ('dev', 'latest', 'v1', or 'legacy', defaults to 'latest') and
                                          // the server to get the data from ('tranquility', 'singularity', defaults to the former)
await esiJS.util.sleep(mills) // pauses execution for the specified amount of time (in miliseconds)
esiJS.util.addArrays(array1, array2) // adds 2 arrays together and returns a merged array
```

esiJS uses [Axios](https://github.com/axios/axios) `v0.19.0`.