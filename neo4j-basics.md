# Tempalte

**Note:** notes




```
docker run \
    --name testneo4j \
    -p7474:7474 -p7687:7687 \
    -d \
    -v $HOME/neo4j/data:/data \
    -v $HOME/neo4j/logs:/logs \
    -v $HOME/neo4j/import:/var/lib/neo4j/import \
    -v $HOME/neo4j/plugins:/plugins \
    --env NEO4J_AUTH=neo4j/test \
    neo4j:latest
```




```
http://localhost:7474/browser/
neo4j/test
```



Connect url:
```
bolt://localhost:7687
neo4j/test
```
[Bolt Protocol](https://en.wikipedia.org/wiki/Bolt_(network_protocol))




```
Keys:
Neo4j Browser
Cypher shell
```




```
docker exec -it testneo4j bash
cypher-shell -u neo4j -p test
```




```
docker exec -it testneo4j bash
cypher-shell -u neo4j -p test
```




```
Social graph
Relationship
    - direction
    - type
    - patterns of data
```

Relationship are data records that can also contain properties



```
Plays:
:play intro
:play cypher
:play start
```




```
http://localhost:7474/browser/
```


Cypher
- Cypher language is built to work with the Graph data
- It uses patterns to describe the graph data
- SQL like


```
    CREATE (ee:Person { name: "Emil", from: "Sweden", klout: 99 });
    CREATE (ee:Person { name: "Raja", from: "Canada", klout: 89 });
    
    MATCH (ee:Person) WHERE ee.name = "Emil" RETURN ee;
    MATCH (ee:Person) WHERE ee.name = "Raja" RETURN ee;
    MATCH (ee:Person) WHERE ee.from = "Canada" RETURN ee;
    
    MATCH (ee:Person) WHERE ee.name = "Emil" RETURN ee;
    
    CREATE (js:Person { name: "Johan", from: "Sweden", learn: "surfing" }),
    (ir:Person { name: "Ian", from: "England", title: "author" }),
    (rvb:Person { name: "Rik", from: "Belgium", pet: "Orval" }),
    (ally:Person { name: "Allison", from: "California", hobby: "surfing" }),
    (ee)-[:KNOWS {since: 2001}]->(js),(ee)-[:KNOWS {rating: 5}]->(ir),
    (js)-[:KNOWS]->(ir),(js)-[:KNOWS]->(rvb),
    (ir)-[:KNOWS]->(js),(ir)-[:KNOWS]->(ally),
    (rvb)-[:KNOWS]->(ally);
```


Select all Nodes
```
MATCH (n)
DETACH DELETE n;
```

Delete all Nodes
```
MATCH (n)
DETACH DELETE n
```


```
    Pattern Matching:
    MATCH (ee:Person)-[:KNOWS]-(friends)
    WHERE ee.name = "Emil" RETURN ee, friends
    
    MATCH (ee:Person) WHERE ee.name = 'Rik' RETURN ee;
    
    MATCH (ee:Person) WHERE ee.from = 'Belgium' RETURN ee;
    
    MATCH (a:Person) WHERE a.pet = 'Orval' RETURN a;
    
    Recommend using patterns:
        MATCH (js:Person)-[:KNOWS]-()-[:KNOWS]-(surfer)
        WHERE js.name = "Johan" AND surfer.hobby = "surfing"
        RETURN DISTINCT surfer
    
        -- Johan's friends who is author
        MATCH (js:Person)-[:KNOWS]-()-[:KNOWS]-(author)
        WHERE js.name = "Johan" AND author.title = "author"
        RETURN DISTINCT author
        
        -- Johan's friends who is from Belgium
        MATCH (js:Person)-[:KNOWS]-()-[:KNOWS]-(user)
        WHERE js.name = "Johan" AND user.from = "Belgium"
        RETURN DISTINCT user;
```




```
    Analyze using visual query plan:
    PROFILE MATCH (js:Person)-[:KNOWS]-()-[:KNOWS]-(surfer)
    WHERE js.name = "Johan" AND surfer.hobby = "surfing"
    RETURN DISTINCT surfer
```




```
How to get the constraints?
    CALL db.constraints;
```
https://stackoverflow.com/questions/21658285/how-do-i-get-the-already-existing-constraints-in-neo4j/52100849




Movie Graph:
```
CREATE (TheMatrix:Movie {title:'The Matrix', released:1999, tagline:'Welcome to the Real World'})
    CREATE (Keanu:Person {name:'Keanu Reeves', born:1964})
    CREATE (Carrie:Person {name:'Carrie-Anne Moss', born:1967})
    CREATE (Laurence:Person {name:'Laurence Fishburne', born:1961})
    CREATE (Hugo:Person {name:'Hugo Weaving', born:1960})
    CREATE (LillyW:Person {name:'Lilly Wachowski', born:1967})
    CREATE (LanaW:Person {name:'Lana Wachowski', born:1965})
    CREATE (JoelS:Person {name:'Joel Silver', born:1952})
    CREATE
      (Keanu)-[:ACTED_IN {roles:['Neo']}]->(TheMatrix),
      (Carrie)-[:ACTED_IN {roles:['Trinity']}]->(TheMatrix),
      (Laurence)-[:ACTED_IN {roles:['Morpheus']}]->(TheMatrix),
      (Hugo)-[:ACTED_IN {roles:['Agent Smith']}]->(TheMatrix),
      (LillyW)-[:DIRECTED]->(TheMatrix),
      (LanaW)-[:DIRECTED]->(TheMatrix),
      (JoelS)-[:PRODUCED]->(TheMatrix)

    CREATE (Emil:Person {name:"Emil Eifrem", born:1978})
    CREATE (Emil)-[:ACTED_IN {roles:["Emil"]}]->(TheMatrix)

    CREATE (TheMatrixReloaded:Movie {title:'The Matrix Reloaded', released:2003, tagline:'Free your mind'})
    CREATE
      (Keanu)-[:ACTED_IN {roles:['Neo']}]->(TheMatrixReloaded),
      (Carrie)-[:ACTED_IN {roles:['Trinity']}]->(TheMatrixReloaded),
      (Laurence)-[:ACTED_IN {roles:['Morpheus']}]->(TheMatrixReloaded),
      (Hugo)-[:ACTED_IN {roles:['Agent Smith']}]->(TheMatrixReloaded),
      (LillyW)-[:DIRECTED]->(TheMatrixReloaded),
      (LanaW)-[:DIRECTED]->(TheMatrixReloaded),
      (JoelS)-[:PRODUCED]->(TheMatrixReloaded)

    CREATE (TheMatrixRevolutions:Movie {title:'The Matrix Revolutions', released:2003, tagline:'Everything that has a beginning has an end'})
    CREATE
      (Keanu)-[:ACTED_IN {roles:['Neo']}]->(TheMatrixRevolutions),
      (Carrie)-[:ACTED_IN {roles:['Trinity']}]->(TheMatrixRevolutions),
      (Laurence)-[:ACTED_IN {roles:['Morpheus']}]->(TheMatrixRevolutions),
      (Hugo)-[:ACTED_IN {roles:['Agent Smith']}]->(TheMatrixRevolutions),
      (LillyW)-[:DIRECTED]->(TheMatrixRevolutions),
      (LanaW)-[:DIRECTED]->(TheMatrixRevolutions),
      (JoelS)-[:PRODUCED]->(TheMatrixRevolutions)

    CREATE (TheDevilsAdvocate:Movie {title:"The Devil's Advocate", released:1997, tagline:'Evil has its winning ways'})
    CREATE (Charlize:Person {name:'Charlize Theron', born:1975})
    CREATE (Al:Person {name:'Al Pacino', born:1940})
    CREATE (Taylor:Person {name:'Taylor Hackford', born:1944})
    CREATE
      (Keanu)-[:ACTED_IN {roles:['Kevin Lomax']}]->(TheDevilsAdvocate),
      (Charlize)-[:ACTED_IN {roles:['Mary Ann Lomax']}]->(TheDevilsAdvocate),
      (Al)-[:ACTED_IN {roles:['John Milton']}]->(TheDevilsAdvocate),
      (Taylor)-[:DIRECTED]->(TheDevilsAdvocate)

    CREATE (AFewGoodMen:Movie {title:"A Few Good Men", released:1992, tagline:"In the heart of the nation's capital, in a courthouse of the U.S. government, one man will stop at nothing to keep his honor, and one will stop at nothing to find the truth."})
    CREATE (TomC:Person {name:'Tom Cruise', born:1962})
    CREATE (JackN:Person {name:'Jack Nicholson', born:1937})
    CREATE (DemiM:Person {name:'Demi Moore', born:1962})
    CREATE (KevinB:Person {name:'Kevin Bacon', born:1958})
    CREATE (KieferS:Person {name:'Kiefer Sutherland', born:1966})
    CREATE (NoahW:Person {name:'Noah Wyle', born:1971})
    CREATE (CubaG:Person {name:'Cuba Gooding Jr.', born:1968})
    CREATE (KevinP:Person {name:'Kevin Pollak', born:1957})
    CREATE (JTW:Person {name:'J.T. Walsh', born:1943})
    CREATE (JamesM:Person {name:'James Marshall', born:1967})
    CREATE (ChristopherG:Person {name:'Christopher Guest', born:1948})
    CREATE (RobR:Person {name:'Rob Reiner', born:1947})
    CREATE (AaronS:Person {name:'Aaron Sorkin', born:1961})
    CREATE
      (TomC)-[:ACTED_IN {roles:['Lt. Daniel Kaffee']}]->(AFewGoodMen),
      (JackN)-[:ACTED_IN {roles:['Col. Nathan R. Jessup']}]->(AFewGoodMen),
      (DemiM)-[:ACTED_IN {roles:['Lt. Cdr. JoAnne Galloway']}]->(AFewGoodMen),
      (KevinB)-[:ACTED_IN {roles:['Capt. Jack Ross']}]->(AFewGoodMen),
      (KieferS)-[:ACTED_IN {roles:['Lt. Jonathan Kendrick']}]->(AFewGoodMen),
      (NoahW)-[:ACTED_IN {roles:['Cpl. Jeffrey Barnes']}]->(AFewGoodMen),
      (CubaG)-[:ACTED_IN {roles:['Cpl. Carl Hammaker']}]->(AFewGoodMen),
      (KevinP)-[:ACTED_IN {roles:['Lt. Sam Weinberg']}]->(AFewGoodMen),
      (JTW)-[:ACTED_IN {roles:['Lt. Col. Matthew Andrew Markinson']}]->(AFewGoodMen),
      (JamesM)-[:ACTED_IN {roles:['Pfc. Louden Downey']}]->(AFewGoodMen),
      (ChristopherG)-[:ACTED_IN {roles:['Dr. Stone']}]->(AFewGoodMen),
      (AaronS)-[:ACTED_IN {roles:['Man in Bar']}]->(AFewGoodMen),
      (RobR)-[:DIRECTED]->(AFewGoodMen),
      (AaronS)-[:WROTE]->(AFewGoodMen)

    CREATE (TopGun:Movie {title:"Top Gun", released:1986, tagline:'I feel the need, the need for speed.'})
    CREATE (KellyM:Person {name:'Kelly McGillis', born:1957})
    CREATE (ValK:Person {name:'Val Kilmer', born:1959})
    CREATE (AnthonyE:Person {name:'Anthony Edwards', born:1962})
    CREATE (TomS:Person {name:'Tom Skerritt', born:1933})
    CREATE (MegR:Person {name:'Meg Ryan', born:1961})
    CREATE (TonyS:Person {name:'Tony Scott', born:1944})
    CREATE (JimC:Person {name:'Jim Cash', born:1941})
    CREATE
      (TomC)-[:ACTED_IN {roles:['Maverick']}]->(TopGun),
      (KellyM)-[:ACTED_IN {roles:['Charlie']}]->(TopGun),
      (ValK)-[:ACTED_IN {roles:['Iceman']}]->(TopGun),
      (AnthonyE)-[:ACTED_IN {roles:['Goose']}]->(TopGun),
      (TomS)-[:ACTED_IN {roles:['Viper']}]->(TopGun),
      (MegR)-[:ACTED_IN {roles:['Carole']}]->(TopGun),
      (TonyS)-[:DIRECTED]->(TopGun),
      (JimC)-[:WROTE]->(TopGun)

    CREATE (JerryMaguire:Movie {title:'Jerry Maguire', released:2000, tagline:'The rest of his life begins now.'})
    CREATE (ReneeZ:Person {name:'Renee Zellweger', born:1969})
    CREATE (KellyP:Person {name:'Kelly Preston', born:1962})
    CREATE (JerryO:Person {name:"Jerry O'Connell", born:1974})
    CREATE (JayM:Person {name:'Jay Mohr', born:1970})
    CREATE (BonnieH:Person {name:'Bonnie Hunt', born:1961})
    CREATE (ReginaK:Person {name:'Regina King', born:1971})
    CREATE (JonathanL:Person {name:'Jonathan Lipnicki', born:1996})
    CREATE (CameronC:Person {name:'Cameron Crowe', born:1957})
    CREATE
      (TomC)-[:ACTED_IN {roles:['Jerry Maguire']}]->(JerryMaguire),
      (CubaG)-[:ACTED_IN {roles:['Rod Tidwell']}]->(JerryMaguire),
      (ReneeZ)-[:ACTED_IN {roles:['Dorothy Boyd']}]->(JerryMaguire),
      (KellyP)-[:ACTED_IN {roles:['Avery Bishop']}]->(JerryMaguire),
      (JerryO)-[:ACTED_IN {roles:['Frank Cushman']}]->(JerryMaguire),
      (JayM)-[:ACTED_IN {roles:['Bob Sugar']}]->(JerryMaguire),
      (BonnieH)-[:ACTED_IN {roles:['Laurel Boyd']}]->(JerryMaguire),
      (ReginaK)-[:ACTED_IN {roles:['Marcee Tidwell']}]->(JerryMaguire),
      (JonathanL)-[:ACTED_IN {roles:['Ray Boyd']}]->(JerryMaguire),
      (CameronC)-[:DIRECTED]->(JerryMaguire),
      (CameronC)-[:PRODUCED]->(JerryMaguire),
      (CameronC)-[:WROTE]->(JerryMaguire)

    CREATE (StandByMe:Movie {title:"Stand By Me", released:1986, tagline:"For some, it's the last real taste of innocence, and the first real taste of life. But for everyone, it's the time that memories are made of."})
    CREATE (RiverP:Person {name:'River Phoenix', born:1970})
    CREATE (CoreyF:Person {name:'Corey Feldman', born:1971})
    CREATE (WilW:Person {name:'Wil Wheaton', born:1972})
    CREATE (JohnC:Person {name:'John Cusack', born:1966})
    CREATE (MarshallB:Person {name:'Marshall Bell', born:1942})
    CREATE
      (WilW)-[:ACTED_IN {roles:['Gordie Lachance']}]->(StandByMe),
      (RiverP)-[:ACTED_IN {roles:['Chris Chambers']}]->(StandByMe),
      (JerryO)-[:ACTED_IN {roles:['Vern Tessio']}]->(StandByMe),
      (CoreyF)-[:ACTED_IN {roles:['Teddy Duchamp']}]->(StandByMe),
      (JohnC)-[:ACTED_IN {roles:['Denny Lachance']}]->(StandByMe),
      (KieferS)-[:ACTED_IN {roles:['Ace Merrill']}]->(StandByMe),
      (MarshallB)-[:ACTED_IN {roles:['Mr. Lachance']}]->(StandByMe),
      (RobR)-[:DIRECTED]->(StandByMe)

    CREATE (AsGoodAsItGets:Movie {title:'As Good as It Gets', released:1997, tagline:'A comedy from the heart that goes for the throat.'})
    CREATE (HelenH:Person {name:'Helen Hunt', born:1963})
    CREATE (GregK:Person {name:'Greg Kinnear', born:1963})
    CREATE (JamesB:Person {name:'James L. Brooks', born:1940})
    CREATE
      (JackN)-[:ACTED_IN {roles:['Melvin Udall']}]->(AsGoodAsItGets),
      (HelenH)-[:ACTED_IN {roles:['Carol Connelly']}]->(AsGoodAsItGets),
      (GregK)-[:ACTED_IN {roles:['Simon Bishop']}]->(AsGoodAsItGets),
      (CubaG)-[:ACTED_IN {roles:['Frank Sachs']}]->(AsGoodAsItGets),
      (JamesB)-[:DIRECTED]->(AsGoodAsItGets)

    CREATE (WhatDreamsMayCome:Movie {title:'What Dreams May Come', released:1998, tagline:'After life there is more. The end is just the beginning.'})
    CREATE (AnnabellaS:Person {name:'Annabella Sciorra', born:1960})
    CREATE (MaxS:Person {name:'Max von Sydow', born:1929})
    CREATE (WernerH:Person {name:'Werner Herzog', born:1942})
    CREATE (Robin:Person {name:'Robin Williams', born:1951})
    CREATE (VincentW:Person {name:'Vincent Ward', born:1956})
    CREATE
      (Robin)-[:ACTED_IN {roles:['Chris Nielsen']}]->(WhatDreamsMayCome),
      (CubaG)-[:ACTED_IN {roles:['Albert Lewis']}]->(WhatDreamsMayCome),
      (AnnabellaS)-[:ACTED_IN {roles:['Annie Collins-Nielsen']}]->(WhatDreamsMayCome),
      (MaxS)-[:ACTED_IN {roles:['The Tracker']}]->(WhatDreamsMayCome),
      (WernerH)-[:ACTED_IN {roles:['The Face']}]->(WhatDreamsMayCome),
      (VincentW)-[:DIRECTED]->(WhatDreamsMayCome)

    CREATE (SnowFallingonCedars:Movie {title:'Snow Falling on Cedars', released:1999, tagline:'First loves last. Forever.'})
    CREATE (EthanH:Person {name:'Ethan Hawke', born:1970})
    CREATE (RickY:Person {name:'Rick Yune', born:1971})
    CREATE (JamesC:Person {name:'James Cromwell', born:1940})
    CREATE (ScottH:Person {name:'Scott Hicks', born:1953})
    CREATE
      (EthanH)-[:ACTED_IN {roles:['Ishmael Chambers']}]->(SnowFallingonCedars),
      (RickY)-[:ACTED_IN {roles:['Kazuo Miyamoto']}]->(SnowFallingonCedars),
      (MaxS)-[:ACTED_IN {roles:['Nels Gudmundsson']}]->(SnowFallingonCedars),
      (JamesC)-[:ACTED_IN {roles:['Judge Fielding']}]->(SnowFallingonCedars),
      (ScottH)-[:DIRECTED]->(SnowFallingonCedars)

    CREATE (YouveGotMail:Movie {title:"You've Got Mail", released:1998, tagline:'At odds in life... in love on-line.'})
    CREATE (ParkerP:Person {name:'Parker Posey', born:1968})
    CREATE (DaveC:Person {name:'Dave Chappelle', born:1973})
    CREATE (SteveZ:Person {name:'Steve Zahn', born:1967})
    CREATE (TomH:Person {name:'Tom Hanks', born:1956})
    CREATE (NoraE:Person {name:'Nora Ephron', born:1941})
    CREATE
      (TomH)-[:ACTED_IN {roles:['Joe Fox']}]->(YouveGotMail),
      (MegR)-[:ACTED_IN {roles:['Kathleen Kelly']}]->(YouveGotMail),
      (GregK)-[:ACTED_IN {roles:['Frank Navasky']}]->(YouveGotMail),
      (ParkerP)-[:ACTED_IN {roles:['Patricia Eden']}]->(YouveGotMail),
      (DaveC)-[:ACTED_IN {roles:['Kevin Jackson']}]->(YouveGotMail),
      (SteveZ)-[:ACTED_IN {roles:['George Pappas']}]->(YouveGotMail),
      (NoraE)-[:DIRECTED]->(YouveGotMail)

    CREATE (SleeplessInSeattle:Movie {title:'Sleepless in Seattle', released:1993, tagline:'What if someone you never met, someone you never saw, someone you never knew was the only someone for you?'})
    CREATE (RitaW:Person {name:'Rita Wilson', born:1956})
    CREATE (BillPull:Person {name:'Bill Pullman', born:1953})
    CREATE (VictorG:Person {name:'Victor Garber', born:1949})
    CREATE (RosieO:Person {name:"Rosie O'Donnell", born:1962})
    CREATE
      (TomH)-[:ACTED_IN {roles:['Sam Baldwin']}]->(SleeplessInSeattle),
      (MegR)-[:ACTED_IN {roles:['Annie Reed']}]->(SleeplessInSeattle),
      (RitaW)-[:ACTED_IN {roles:['Suzy']}]->(SleeplessInSeattle),
      (BillPull)-[:ACTED_IN {roles:['Walter']}]->(SleeplessInSeattle),
      (VictorG)-[:ACTED_IN {roles:['Greg']}]->(SleeplessInSeattle),
      (RosieO)-[:ACTED_IN {roles:['Becky']}]->(SleeplessInSeattle),
      (NoraE)-[:DIRECTED]->(SleeplessInSeattle)

    CREATE (JoeVersustheVolcano:Movie {title:'Joe Versus the Volcano', released:1990, tagline:'A story of love, lava and burning desire.'})
    CREATE (JohnS:Person {name:'John Patrick Stanley', born:1950})
    CREATE (Nathan:Person {name:'Nathan Lane', born:1956})
    CREATE
      (TomH)-[:ACTED_IN {roles:['Joe Banks']}]->(JoeVersustheVolcano),
      (MegR)-[:ACTED_IN {roles:['DeDe', 'Angelica Graynamore', 'Patricia Graynamore']}]->(JoeVersustheVolcano),
      (Nathan)-[:ACTED_IN {roles:['Baw']}]->(JoeVersustheVolcano),
      (JohnS)-[:DIRECTED]->(JoeVersustheVolcano)

    CREATE (WhenHarryMetSally:Movie {title:'When Harry Met Sally', released:1998, tagline:'Can two friends sleep together and still love each other in the morning?'})
    CREATE (BillyC:Person {name:'Billy Crystal', born:1948})
    CREATE (CarrieF:Person {name:'Carrie Fisher', born:1956})
    CREATE (BrunoK:Person {name:'Bruno Kirby', born:1949})
    CREATE
      (BillyC)-[:ACTED_IN {roles:['Harry Burns']}]->(WhenHarryMetSally),
      (MegR)-[:ACTED_IN {roles:['Sally Albright']}]->(WhenHarryMetSally),
      (CarrieF)-[:ACTED_IN {roles:['Marie']}]->(WhenHarryMetSally),
      (BrunoK)-[:ACTED_IN {roles:['Jess']}]->(WhenHarryMetSally),
      (RobR)-[:DIRECTED]->(WhenHarryMetSally),
      (RobR)-[:PRODUCED]->(WhenHarryMetSally),
      (NoraE)-[:PRODUCED]->(WhenHarryMetSally),
      (NoraE)-[:WROTE]->(WhenHarryMetSally)

    CREATE (ThatThingYouDo:Movie {title:'That Thing You Do', released:1996, tagline:'In every life there comes a time when that thing you dream becomes that thing you do'})
    CREATE (LivT:Person {name:'Liv Tyler', born:1977})
    CREATE
      (TomH)-[:ACTED_IN {roles:['Mr. White']}]->(ThatThingYouDo),
      (LivT)-[:ACTED_IN {roles:['Faye Dolan']}]->(ThatThingYouDo),
      (Charlize)-[:ACTED_IN {roles:['Tina']}]->(ThatThingYouDo),
      (TomH)-[:DIRECTED]->(ThatThingYouDo)

    CREATE (TheReplacements:Movie {title:'The Replacements', released:2000, tagline:'Pain heals, Chicks dig scars... Glory lasts forever'})
    CREATE (Brooke:Person {name:'Brooke Langton', born:1970})
    CREATE (Gene:Person {name:'Gene Hackman', born:1930})
    CREATE (Orlando:Person {name:'Orlando Jones', born:1968})
    CREATE (Howard:Person {name:'Howard Deutch', born:1950})
    CREATE
      (Keanu)-[:ACTED_IN {roles:['Shane Falco']}]->(TheReplacements),
      (Brooke)-[:ACTED_IN {roles:['Annabelle Farrell']}]->(TheReplacements),
      (Gene)-[:ACTED_IN {roles:['Jimmy McGinty']}]->(TheReplacements),
      (Orlando)-[:ACTED_IN {roles:['Clifford Franklin']}]->(TheReplacements),
      (Howard)-[:DIRECTED]->(TheReplacements)

    CREATE (RescueDawn:Movie {title:'RescueDawn', released:2006, tagline:"Based on the extraordinary true story of one man's fight for freedom"})
    CREATE (ChristianB:Person {name:'Christian Bale', born:1974})
    CREATE (ZachG:Person {name:'Zach Grenier', born:1954})
    CREATE
      (MarshallB)-[:ACTED_IN {roles:['Admiral']}]->(RescueDawn),
      (ChristianB)-[:ACTED_IN {roles:['Dieter Dengler']}]->(RescueDawn),
      (ZachG)-[:ACTED_IN {roles:['Squad Leader']}]->(RescueDawn),
      (SteveZ)-[:ACTED_IN {roles:['Duane']}]->(RescueDawn),
      (WernerH)-[:DIRECTED]->(RescueDawn)

    CREATE (TheBirdcage:Movie {title:'The Birdcage', released:1996, tagline:'Come as you are'})
    CREATE (MikeN:Person {name:'Mike Nichols', born:1931})
    CREATE
      (Robin)-[:ACTED_IN {roles:['Armand Goldman']}]->(TheBirdcage),
      (Nathan)-[:ACTED_IN {roles:['Albert Goldman']}]->(TheBirdcage),
      (Gene)-[:ACTED_IN {roles:['Sen. Kevin Keeley']}]->(TheBirdcage),
      (MikeN)-[:DIRECTED]->(TheBirdcage)

    CREATE (Unforgiven:Movie {title:'Unforgiven', released:1992, tagline:"It's a hell of a thing, killing a man"})
    CREATE (RichardH:Person {name:'Richard Harris', born:1930})
    CREATE (ClintE:Person {name:'Clint Eastwood', born:1930})
    CREATE
      (RichardH)-[:ACTED_IN {roles:['English Bob']}]->(Unforgiven),
      (ClintE)-[:ACTED_IN {roles:['Bill Munny']}]->(Unforgiven),
      (Gene)-[:ACTED_IN {roles:['Little Bill Daggett']}]->(Unforgiven),
      (ClintE)-[:DIRECTED]->(Unforgiven)

    CREATE (JohnnyMnemonic:Movie {title:'Johnny Mnemonic', released:1995, tagline:'The hottest data on earth. In the coolest head in town'})
    CREATE (Takeshi:Person {name:'Takeshi Kitano', born:1947})
    CREATE (Dina:Person {name:'Dina Meyer', born:1968})
    CREATE (IceT:Person {name:'Ice-T', born:1958})
    CREATE (RobertL:Person {name:'Robert Longo', born:1953})
    CREATE
      (Keanu)-[:ACTED_IN {roles:['Johnny Mnemonic']}]->(JohnnyMnemonic),
      (Takeshi)-[:ACTED_IN {roles:['Takahashi']}]->(JohnnyMnemonic),
      (Dina)-[:ACTED_IN {roles:['Jane']}]->(JohnnyMnemonic),
      (IceT)-[:ACTED_IN {roles:['J-Bone']}]->(JohnnyMnemonic),
      (RobertL)-[:DIRECTED]->(JohnnyMnemonic)

    CREATE (CloudAtlas:Movie {title:'Cloud Atlas', released:2012, tagline:'Everything is connected'})
    CREATE (HalleB:Person {name:'Halle Berry', born:1966})
    CREATE (JimB:Person {name:'Jim Broadbent', born:1949})
    CREATE (TomT:Person {name:'Tom Tykwer', born:1965})
    CREATE (DavidMitchell:Person {name:'David Mitchell', born:1969})
    CREATE (StefanArndt:Person {name:'Stefan Arndt', born:1961})
    CREATE
      (TomH)-[:ACTED_IN {roles:['Zachry', 'Dr. Henry Goose', 'Isaac Sachs', 'Dermot Hoggins']}]->(CloudAtlas),
      (Hugo)-[:ACTED_IN {roles:['Bill Smoke', 'Haskell Moore', 'Tadeusz Kesselring', 'Nurse Noakes', 'Boardman Mephi', 'Old Georgie']}]->(CloudAtlas),
      (HalleB)-[:ACTED_IN {roles:['Luisa Rey', 'Jocasta Ayrs', 'Ovid', 'Meronym']}]->(CloudAtlas),
      (JimB)-[:ACTED_IN {roles:['Vyvyan Ayrs', 'Captain Molyneux', 'Timothy Cavendish']}]->(CloudAtlas),
      (TomT)-[:DIRECTED]->(CloudAtlas),
      (LillyW)-[:DIRECTED]->(CloudAtlas),
      (LanaW)-[:DIRECTED]->(CloudAtlas),
      (DavidMitchell)-[:WROTE]->(CloudAtlas),
      (StefanArndt)-[:PRODUCED]->(CloudAtlas)

    CREATE (TheDaVinciCode:Movie {title:'The Da Vinci Code', released:2006, tagline:'Break The Codes'})
    CREATE (IanM:Person {name:'Ian McKellen', born:1939})
    CREATE (AudreyT:Person {name:'Audrey Tautou', born:1976})
    CREATE (PaulB:Person {name:'Paul Bettany', born:1971})
    CREATE (RonH:Person {name:'Ron Howard', born:1954})
    CREATE
      (TomH)-[:ACTED_IN {roles:['Dr. Robert Langdon']}]->(TheDaVinciCode),
      (IanM)-[:ACTED_IN {roles:['Sir Leight Teabing']}]->(TheDaVinciCode),
      (AudreyT)-[:ACTED_IN {roles:['Sophie Neveu']}]->(TheDaVinciCode),
      (PaulB)-[:ACTED_IN {roles:['Silas']}]->(TheDaVinciCode),
      (RonH)-[:DIRECTED]->(TheDaVinciCode)

    CREATE (VforVendetta:Movie {title:'V for Vendetta', released:2006, tagline:'Freedom! Forever!'})
    CREATE (NatalieP:Person {name:'Natalie Portman', born:1981})
    CREATE (StephenR:Person {name:'Stephen Rea', born:1946})
    CREATE (JohnH:Person {name:'John Hurt', born:1940})
    CREATE (BenM:Person {name: 'Ben Miles', born:1967})
    CREATE
      (Hugo)-[:ACTED_IN {roles:['V']}]->(VforVendetta),
      (NatalieP)-[:ACTED_IN {roles:['Evey Hammond']}]->(VforVendetta),
      (StephenR)-[:ACTED_IN {roles:['Eric Finch']}]->(VforVendetta),
      (JohnH)-[:ACTED_IN {roles:['High Chancellor Adam Sutler']}]->(VforVendetta),
      (BenM)-[:ACTED_IN {roles:['Dascomb']}]->(VforVendetta),
      (JamesM)-[:DIRECTED]->(VforVendetta),
      (LillyW)-[:PRODUCED]->(VforVendetta),
      (LanaW)-[:PRODUCED]->(VforVendetta),
      (JoelS)-[:PRODUCED]->(VforVendetta),
      (LillyW)-[:WROTE]->(VforVendetta),
      (LanaW)-[:WROTE]->(VforVendetta)

    CREATE (SpeedRacer:Movie {title:'Speed Racer', released:2008, tagline:'Speed has no limits'})
    CREATE (EmileH:Person {name:'Emile Hirsch', born:1985})
    CREATE (JohnG:Person {name:'John Goodman', born:1960})
    CREATE (SusanS:Person {name:'Susan Sarandon', born:1946})
    CREATE (MatthewF:Person {name:'Matthew Fox', born:1966})
    CREATE (ChristinaR:Person {name:'Christina Ricci', born:1980})
    CREATE (Rain:Person {name:'Rain', born:1982})
    CREATE
      (EmileH)-[:ACTED_IN {roles:['Speed Racer']}]->(SpeedRacer),
      (JohnG)-[:ACTED_IN {roles:['Pops']}]->(SpeedRacer),
      (SusanS)-[:ACTED_IN {roles:['Mom']}]->(SpeedRacer),
      (MatthewF)-[:ACTED_IN {roles:['Racer X']}]->(SpeedRacer),
      (ChristinaR)-[:ACTED_IN {roles:['Trixie']}]->(SpeedRacer),
      (Rain)-[:ACTED_IN {roles:['Taejo Togokahn']}]->(SpeedRacer),
      (BenM)-[:ACTED_IN {roles:['Cass Jones']}]->(SpeedRacer),
      (LillyW)-[:DIRECTED]->(SpeedRacer),
      (LanaW)-[:DIRECTED]->(SpeedRacer),
      (LillyW)-[:WROTE]->(SpeedRacer),
      (LanaW)-[:WROTE]->(SpeedRacer),
      (JoelS)-[:PRODUCED]->(SpeedRacer)

    CREATE (NinjaAssassin:Movie {title:'Ninja Assassin', released:2009, tagline:'Prepare to enter a secret world of assassins'})
    CREATE (NaomieH:Person {name:'Naomie Harris'})
    CREATE
      (Rain)-[:ACTED_IN {roles:['Raizo']}]->(NinjaAssassin),
      (NaomieH)-[:ACTED_IN {roles:['Mika Coretti']}]->(NinjaAssassin),
      (RickY)-[:ACTED_IN {roles:['Takeshi']}]->(NinjaAssassin),
      (BenM)-[:ACTED_IN {roles:['Ryan Maslow']}]->(NinjaAssassin),
      (JamesM)-[:DIRECTED]->(NinjaAssassin),
      (LillyW)-[:PRODUCED]->(NinjaAssassin),
      (LanaW)-[:PRODUCED]->(NinjaAssassin),
      (JoelS)-[:PRODUCED]->(NinjaAssassin)

    CREATE (TheGreenMile:Movie {title:'The Green Mile', released:1999, tagline:"Walk a mile you'll never forget."})
    CREATE (MichaelD:Person {name:'Michael Clarke Duncan', born:1957})
    CREATE (DavidM:Person {name:'David Morse', born:1953})
    CREATE (SamR:Person {name:'Sam Rockwell', born:1968})
    CREATE (GaryS:Person {name:'Gary Sinise', born:1955})
    CREATE (PatriciaC:Person {name:'Patricia Clarkson', born:1959})
    CREATE (FrankD:Person {name:'Frank Darabont', born:1959})
    CREATE
      (TomH)-[:ACTED_IN {roles:['Paul Edgecomb']}]->(TheGreenMile),
      (MichaelD)-[:ACTED_IN {roles:['John Coffey']}]->(TheGreenMile),
      (DavidM)-[:ACTED_IN {roles:['Brutus "Brutal" Howell']}]->(TheGreenMile),
      (BonnieH)-[:ACTED_IN {roles:['Jan Edgecomb']}]->(TheGreenMile),
      (JamesC)-[:ACTED_IN {roles:['Warden Hal Moores']}]->(TheGreenMile),
      (SamR)-[:ACTED_IN {roles:['"Wild Bill" Wharton']}]->(TheGreenMile),
      (GaryS)-[:ACTED_IN {roles:['Burt Hammersmith']}]->(TheGreenMile),
      (PatriciaC)-[:ACTED_IN {roles:['Melinda Moores']}]->(TheGreenMile),
      (FrankD)-[:DIRECTED]->(TheGreenMile)

    CREATE (FrostNixon:Movie {title:'Frost/Nixon', released:2008, tagline:'400 million people were waiting for the truth.'})
    CREATE (FrankL:Person {name:'Frank Langella', born:1938})
    CREATE (MichaelS:Person {name:'Michael Sheen', born:1969})
    CREATE (OliverP:Person {name:'Oliver Platt', born:1960})
    CREATE
      (FrankL)-[:ACTED_IN {roles:['Richard Nixon']}]->(FrostNixon),
      (MichaelS)-[:ACTED_IN {roles:['David Frost']}]->(FrostNixon),
      (KevinB)-[:ACTED_IN {roles:['Jack Brennan']}]->(FrostNixon),
      (OliverP)-[:ACTED_IN {roles:['Bob Zelnick']}]->(FrostNixon),
      (SamR)-[:ACTED_IN {roles:['James Reston, Jr.']}]->(FrostNixon),
      (RonH)-[:DIRECTED]->(FrostNixon)

    CREATE (Hoffa:Movie {title:'Hoffa', released:1992, tagline:"He didn't want law. He wanted justice."})
    CREATE (DannyD:Person {name:'Danny DeVito', born:1944})
    CREATE (JohnR:Person {name:'John C. Reilly', born:1965})
    CREATE
      (JackN)-[:ACTED_IN {roles:['Hoffa']}]->(Hoffa),
      (DannyD)-[:ACTED_IN {roles:['Robert "Bobby" Ciaro']}]->(Hoffa),
      (JTW)-[:ACTED_IN {roles:['Frank Fitzsimmons']}]->(Hoffa),
      (JohnR)-[:ACTED_IN {roles:['Peter "Pete" Connelly']}]->(Hoffa),
      (DannyD)-[:DIRECTED]->(Hoffa)

    CREATE (Apollo13:Movie {title:'Apollo 13', released:1995, tagline:'Houston, we have a problem.'})
    CREATE (EdH:Person {name:'Ed Harris', born:1950})
    CREATE (BillPax:Person {name:'Bill Paxton', born:1955})
    CREATE
      (TomH)-[:ACTED_IN {roles:['Jim Lovell']}]->(Apollo13),
      (KevinB)-[:ACTED_IN {roles:['Jack Swigert']}]->(Apollo13),
      (EdH)-[:ACTED_IN {roles:['Gene Kranz']}]->(Apollo13),
      (BillPax)-[:ACTED_IN {roles:['Fred Haise']}]->(Apollo13),
      (GaryS)-[:ACTED_IN {roles:['Ken Mattingly']}]->(Apollo13),
      (RonH)-[:DIRECTED]->(Apollo13)

    CREATE (Twister:Movie {title:'Twister', released:1996, tagline:"Don't Breathe. Don't Look Back."})
    CREATE (PhilipH:Person {name:'Philip Seymour Hoffman', born:1967})
    CREATE (JanB:Person {name:'Jan de Bont', born:1943})
    CREATE
      (BillPax)-[:ACTED_IN {roles:['Bill Harding']}]->(Twister),
      (HelenH)-[:ACTED_IN {roles:['Dr. Jo Harding']}]->(Twister),
      (ZachG)-[:ACTED_IN {roles:['Eddie']}]->(Twister),
      (PhilipH)-[:ACTED_IN {roles:['Dustin "Dusty" Davis']}]->(Twister),
      (JanB)-[:DIRECTED]->(Twister)

    CREATE (CastAway:Movie {title:'Cast Away', released:2000, tagline:'At the edge of the world, his journey begins.'})
    CREATE (RobertZ:Person {name:'Robert Zemeckis', born:1951})
    CREATE
      (TomH)-[:ACTED_IN {roles:['Chuck Noland']}]->(CastAway),
      (HelenH)-[:ACTED_IN {roles:['Kelly Frears']}]->(CastAway),
      (RobertZ)-[:DIRECTED]->(CastAway)

    CREATE (OneFlewOvertheCuckoosNest:Movie {title:"One Flew Over the Cuckoo's Nest", released:1975, tagline:"If he's crazy, what does that make you?"})
    CREATE (MilosF:Person {name:'Milos Forman', born:1932})
    CREATE
      (JackN)-[:ACTED_IN {roles:['Randle McMurphy']}]->(OneFlewOvertheCuckoosNest),
      (DannyD)-[:ACTED_IN {roles:['Martini']}]->(OneFlewOvertheCuckoosNest),
      (MilosF)-[:DIRECTED]->(OneFlewOvertheCuckoosNest)

    CREATE (SomethingsGottaGive:Movie {title:"Something's Gotta Give", released:2003})
    CREATE (DianeK:Person {name:'Diane Keaton', born:1946})
    CREATE (NancyM:Person {name:'Nancy Meyers', born:1949})
    CREATE
      (JackN)-[:ACTED_IN {roles:['Harry Sanborn']}]->(SomethingsGottaGive),
      (DianeK)-[:ACTED_IN {roles:['Erica Barry']}]->(SomethingsGottaGive),
      (Keanu)-[:ACTED_IN {roles:['Julian Mercer']}]->(SomethingsGottaGive),
      (NancyM)-[:DIRECTED]->(SomethingsGottaGive),
      (NancyM)-[:PRODUCED]->(SomethingsGottaGive),
      (NancyM)-[:WROTE]->(SomethingsGottaGive)

    CREATE (BicentennialMan:Movie {title:'Bicentennial Man', released:1999, tagline:"One robot's 200 year journey to become an ordinary man."})
    CREATE (ChrisC:Person {name:'Chris Columbus', born:1958})
    CREATE
      (Robin)-[:ACTED_IN {roles:['Andrew Marin']}]->(BicentennialMan),
      (OliverP)-[:ACTED_IN {roles:['Rupert Burns']}]->(BicentennialMan),
      (ChrisC)-[:DIRECTED]->(BicentennialMan)

    CREATE (CharlieWilsonsWar:Movie {title:"Charlie Wilson's War", released:2007, tagline:"A stiff drink. A little mascara. A lot of nerve. Who said they couldn't bring down the Soviet empire."})
    CREATE (JuliaR:Person {name:'Julia Roberts', born:1967})
    CREATE
      (TomH)-[:ACTED_IN {roles:['Rep. Charlie Wilson']}]->(CharlieWilsonsWar),
      (JuliaR)-[:ACTED_IN {roles:['Joanne Herring']}]->(CharlieWilsonsWar),
      (PhilipH)-[:ACTED_IN {roles:['Gust Avrakotos']}]->(CharlieWilsonsWar),
      (MikeN)-[:DIRECTED]->(CharlieWilsonsWar)

    CREATE (ThePolarExpress:Movie {title:'The Polar Express', released:2004, tagline:'This Holiday Season… Believe'})
    CREATE
      (TomH)-[:ACTED_IN {roles:['Hero Boy', 'Father', 'Conductor', 'Hobo', 'Scrooge', 'Santa Claus']}]->(ThePolarExpress),
      (RobertZ)-[:DIRECTED]->(ThePolarExpress)

    CREATE (ALeagueofTheirOwn:Movie {title:'A League of Their Own', released:1992, tagline:'Once in a lifetime you get a chance to do something different.'})
    CREATE (Madonna:Person {name:'Madonna', born:1954})
    CREATE (GeenaD:Person {name:'Geena Davis', born:1956})
    CREATE (LoriP:Person {name:'Lori Petty', born:1963})
    CREATE (PennyM:Person {name:'Penny Marshall', born:1943})
    CREATE
      (TomH)-[:ACTED_IN {roles:['Jimmy Dugan']}]->(ALeagueofTheirOwn),
      (GeenaD)-[:ACTED_IN {roles:['Dottie Hinson']}]->(ALeagueofTheirOwn),
      (LoriP)-[:ACTED_IN {roles:['Kit Keller']}]->(ALeagueofTheirOwn),
      (RosieO)-[:ACTED_IN {roles:['Doris Murphy']}]->(ALeagueofTheirOwn),
      (Madonna)-[:ACTED_IN {roles:['"All the Way" Mae Mordabito']}]->(ALeagueofTheirOwn),
      (BillPax)-[:ACTED_IN {roles:['Bob Hinson']}]->(ALeagueofTheirOwn),
      (PennyM)-[:DIRECTED]->(ALeagueofTheirOwn)

    CREATE (PaulBlythe:Person {name:'Paul Blythe'})
    CREATE (AngelaScope:Person {name:'Angela Scope'})
    CREATE (JessicaThompson:Person {name:'Jessica Thompson'})
    CREATE (JamesThompson:Person {name:'James Thompson'})

    CREATE
      (JamesThompson)-[:FOLLOWS]->(JessicaThompson),
      (AngelaScope)-[:FOLLOWS]->(JessicaThompson),
      (PaulBlythe)-[:FOLLOWS]->(AngelaScope)

    CREATE
      (JessicaThompson)-[:REVIEWED {summary:'An amazing journey', rating:95}]->(CloudAtlas),
      (JessicaThompson)-[:REVIEWED {summary:'Silly, but fun', rating:65}]->(TheReplacements),
      (JamesThompson)-[:REVIEWED {summary:'The coolest football movie ever', rating:100}]->(TheReplacements),
      (AngelaScope)-[:REVIEWED {summary:'Pretty funny at times', rating:62}]->(TheReplacements),
      (JessicaThompson)-[:REVIEWED {summary:'Dark, but compelling', rating:85}]->(Unforgiven),
      (JessicaThompson)-[:REVIEWED {summary:"Slapstick redeemed only by the Robin Williams and Gene Hackman's stellar performances", rating:45}]->(TheBirdcage),
      (JessicaThompson)-[:REVIEWED {summary:'A solid romp', rating:68}]->(TheDaVinciCode),
      (JamesThompson)-[:REVIEWED {summary:'Fun, but a little far fetched', rating:65}]->(TheDaVinciCode),
      (JessicaThompson)-[:REVIEWED {summary:'You had me at Jerry', rating:92}]->(JerryMaguire)

    WITH TomH as a
    MATCH (a)-[:ACTED_IN]->(m)<-[:DIRECTED]-(d) RETURN a,m,d LIMIT 10
    ;
    
    Find the actor named "Tom Hanks":
    MATCH (tom {name: "Tom Hanks"}) RETURN tom;
    
    Find the movie with title "Cloud Atlas":
    MATCH (cloudAtlas {title: "Cloud Atlas"}) RETURN cloudAtlas;
    
    Find the movie with title "Cloud Atlas":
    MATCH (abc {title: "Cloud Atlas"}) RETURN abc;
    
    Find 10 people:
    MATCH (people:Person) RETURN people.name LIMIT 10;
    
    Find 100 people:
    MATCH (people:Person) RETURN people.name LIMIT 100;
    
    "Emil"
    "Keanu Reeves"
    "Carrie-Anne Moss"
    "Laurence Fishburne"
    "Hugo Weaving"
    "Lilly Wachowski"
    "Lana Wachowski"
    "Joel Silver"
    "Emil Eifrem"
    "Charlize Theron"
    "Al Pacino"
    "Taylor Hackford"
    "Tom Cruise"
    "Jack Nicholson"
    "Demi Moore"
    "Raja"
    "Johan"
    "Ian"
    "Rik"
    "Allison"
    "Kevin Bacon"
    "Kiefer Sutherland"
    "Noah Wyle"
    "Cuba Gooding Jr."
    "Kevin Pollak"
    "J.T. Walsh"
    "James Marshall"
    "Christopher Guest"
    "Rob Reiner"
    "Aaron Sorkin"
    "Kelly McGillis"
    "Val Kilmer"
    "Anthony Edwards"
    "Tom Skerritt"
    "Meg Ryan"
    "Tony Scott"
    "Jim Cash"
    "Renee Zellweger"
    "Kelly Preston"
    "Jerry O'Connell"
    "Jay Mohr"
    "Bonnie Hunt"
    "Regina King"
    "Jonathan Lipnicki"
    "Cameron Crowe"
    "River Phoenix"
    "Corey Feldman"
    "Wil Wheaton"
    "John Cusack"
    "Marshall Bell"
    "Helen Hunt"
    "Greg Kinnear"
    "James L. Brooks"
    "Annabella Sciorra"
    "Max von Sydow"
    "Werner Herzog"
    "Robin Williams"
    "Vincent Ward"
    "Ethan Hawke"
    "Rick Yune"
    "James Cromwell"
    "Scott Hicks"
    "Parker Posey"
    "Dave Chappelle"
    "Steve Zahn"
    "Tom Hanks"
    "Nora Ephron"
    "Rita Wilson"
    "Bill Pullman"
    "Victor Garber"
    "Rosie O'Donnell"
    "John Patrick Stanley"
    "Nathan Lane"
    "Billy Crystal"
    "Carrie Fisher"
    "Bruno Kirby"
    "Liv Tyler"
    "Brooke Langton"
    "Gene Hackman"
    "Orlando Jones"
    "Howard Deutch"
    "Christian Bale"
    "Zach Grenier"
    "Mike Nichols"
    "Richard Harris"
    "Clint Eastwood"
    "Takeshi Kitano"
    "Dina Meyer"
    "Ice-T"
    "Robert Longo"
    "Halle Berry"
    "Jim Broadbent"
    "Tom Tykwer"
    "David Mitchell"
    "Stefan Arndt"
    "Ian McKellen"
    "Audrey Tautou"
    "Paul Bettany"
    "Ron Howard"
    "Natalie Portman"
    
    Find 5 Movie titles:
    MATCH (movie:Movie) RETURN movie.title LIMIT 5;
    
    Find 50 Movie titles:
    MATCH (movie:Movie) RETURN movie.title LIMIT 50;
    
    "The Matrix"
    "The Matrix Reloaded"
    "The Matrix Revolutions"
    "The Devil's Advocate"
    "A Few Good Men"
    "Top Gun"
    "Jerry Maguire"
    "Stand By Me"
    "As Good as It Gets"
    "What Dreams May Come"
    "Snow Falling on Cedars"
    "You've Got Mail"
    "Sleepless in Seattle"
    "Joe Versus the Volcano"
    "When Harry Met Sally"
    "That Thing You Do"
    "The Replacements"
    "RescueDawn"
    "The Birdcage"
    "Unforgiven"
    "Johnny Mnemonic"
    "Cloud Atlas"
    "The Da Vinci Code"
    "V for Vendetta"
    "Speed Racer"
    "Ninja Assassin"
    "The Green Mile"
    "Frost/Nixon"
    "Hoffa"
    "Apollo 13"
    "Twister"
    "Cast Away"
    "One Flew Over the Cuckoo's Nest"
    "Something's Gotta Give"
    "Bicentennial Man"
    "Charlie Wilson's War"
    "The Polar Express"
    "A League of Their Own"


    Find 4 people:
    MATCH (a:Person) RETURN a.name LIMIT 4;
    
    Find movies released in the 1990s...:
    MATCH (nineties:Movie) WHERE nineties.released >= 1990 AND nineties.released < 2000 RETURN nineties.title;
    
    
    MATCH (tom:Person {name: "Tom Hanks"})-[:ACTED_IN]->(tomHanksMovies) RETURN tom,tomHanksMovies;
    
    
    MATCH (nat:Person {name: "Natalie Portman"})-[:ACTED_IN]->(natMovies) RETURN nat,natMovies;
    
    
    MATCH (cloudAtlas {title: "Cloud Atlas"})<-[:DIRECTED]-(directors) RETURN directors.name;
    
    -- Who is the director of the movie Hoffa?
    MATCH (hoffa {title: "Hoffa"})<-[:DIRECTED]-(directors) RETURN directors.name;
    
    -- Who is the director of the movie Twister?
    MATCH (tw {title : "Twister"})<-[:DIRECTED]-(directors) RETURN directors.name;

    -- How people are related to "Cloud Atlas"...
    MATCH (people:Person)-[relatedTo]-(:Movie {title: "Cloud Atlas"}) RETURN people.name, Type(relatedTo), relatedTo;
    
    
    MATCH (bacon:Person {name:"Kevin Bacon"})-[*1..4]-(hollywood)
    RETURN DISTINCT hollywood;
    
    MATCH p=shortestPath(
      (bacon:Person {name:"Kevin Bacon"})-[*]-(meg:Person {name:"Meg Ryan"})
    )
    RETURN p
    
    -- Extend Tom Hanks co-actors, to find co-co-actors who haven't worked with Tom Hanks...
    MATCH (tom:Person {name:"Tom Hanks"})-[:ACTED_IN]->(m)<-[:ACTED_IN]-(coActors),
          (coActors)-[:ACTED_IN]->(m2)<-[:ACTED_IN]-(cocoActors)
    WHERE NOT (tom)-[:ACTED_IN]->()<-[:ACTED_IN]-(cocoActors) AND tom <> cocoActors
    RETURN cocoActors.name AS Recommended, count(*) AS Strength ORDER BY Strength DESC
    
    -- Find someone to introduce Tom Hanks to Tom Cruise
    MATCH (tom:Person {name:"Tom Hanks"})-[:ACTED_IN]->(m)<-[:ACTED_IN]-(coActors),
          (coActors)-[:ACTED_IN]->(m2)<-[:ACTED_IN]-(cruise:Person {name:"Tom Cruise"})
    RETURN tom, m, coActors, m2, cruise;
    
    -- Delete all nodes
    MATCH (n) DETACH DELETE n;
    
    -- Check nodes
    MATCH (n) RETURN n;
```



Tamil Movies:
```
Asuran:

    CREATE (Asuran:Movie {title:"Asuran", released:2019, tagline:'Bring the justice'})
    
    CREATE (Dhanush:Person {name:'Dhanush', born:1983})
    CREATE (ManjuWarrier:Person {name:'Manju Warrier', born:1978})
    
    CREATE (GVPrakash:Person {name:'G V Prakash Kumar', born:1987})
    CREATE (Vetrimaaran:Person {name:'Vetrimaaran', born:1975})
    
    CREATE (SuKa:Person {name:'SuKa', born:1975})
    
    CREATE
      (Dhanush)-[:ACTED_IN {roles:['Hero']}]->(Asuran),
      (ManjuWarrier)-[:ACTED_IN {roles:['Heroine']}]->(Asuran),
      (GVPrakash)-[:MUSIC]->(Asuran),
      (Vetrimaaran)-[:DIRECTED]->(Asuran),
      (SuKa)-[:WROTE]->(Asuran)
      
      MATCH (tw {title : "Asuran"})<-[:DIRECTED]-(directors) RETURN directors.name;
      MATCH (tw {title : "Twister"})<-[:DIRECTED]-(directors) RETURN directors.name;

      MATCH (p:Person) RETURN p.name LIMIT 50;
      MATCH (p:Person {name : "Dhanush"}) RETURN p.name LIMIT 50;
      
      MATCH (p:Person {name : "Dhanush"}) RETURN p LIMIT 50;

      MATCH (p:Person) where ID(p)=1 RETURN p
      
      MATCH (p:Person {name : "Dhanush"}) where ID(p)=1 RETURN p;
      
      MATCH (p:Person {name : "Dhanush"}) RETURN p.ID; // not gonna work
      
      MATCH (p:Person) RETURN ID(p) LIMIT 5;
      
      MATCH (p:Person {name : "Dhanush"}) RETURN ID(p) LIMIT 5;

      -- Delete Person by id
      MATCH (p:Person) where ID(p)=219
      OPTIONAL MATCH (p)-[r]-() //drops p's relations
      DELETE r,p;
      
      MATCH (m:Movie {title : "Asuran"}) RETURN ID(m), m;
      
      MATCH (m:Movie {title : "Asuran"}) RETURN ID(m);
      MATCH (m {title : "Asuran"})<-[:DIRECTED]-(directors) RETURN directors.name;
      MATCH (m {title : "Asuran"})<-[:ACTED_IN]-(actor) RETURN actor.name;
      
      -- Delete Movie by id
      MATCH (p:Movie) where ID(p)=218
      OPTIONAL MATCH (p)-[r]-() //drops p's relations
      DELETE r,p;
      
      MATCH (p:Person) RETURN ID(p), p LIMIT 50;
      
      MATCH (p:Person {})
      
      MATCH (p:Person {name : "Manju Warrier"}) RETURN ID(p), p;
      220
      
      MATCH (p:Person {name : "G V Prakash Kumar"}) RETURN ID(p), p;
      221
      
      MATCH (p:Person) where ID(p) IN [220, 221]
      OPTIONAL MATCH (p)-[r]-() //drops p's relations
      DELETE r,p;
          https://stackoverflow.com/questions/38311427/how-to-have-multiple-ids-in-the-where-clause-in-neo4j
      
      
      START n=node(*) RETURN n;
      MATCH (n) RETURN (n);
          https://stackoverflow.com/questions/8372788/show-all-nodes-and-relationships-in-data-browser-tab
          
          
     START n=node(*) MATCH (n)-[r]->(m) RETURN ID(n), n,r,m;
         https://stackoverflow.com/questions/8372788/show-all-nodes-and-relationships-in-data-browser-tab
         
    START n=node(*) MATCH (n)-[r]->(m) RETURN ID(n), n,r,m;
    
    MATCH (people:Person)-[relatedTo]-(:Movie {title: "Asuran"}) RETURN people.name, Type(relatedTo), relatedTo;
    
    
    MATCH (bacon:Person {name:"Dhanush"})-[*1..4]-(hollywood)
    RETURN DISTINCT hollywood;
```




```
Bigil

    CREATE (Bigil:Movie {title:'Bigil', released:2019, tagline:'Bend it like Beckham'});
    CREATE (Vijay:Person {name:'Vijay', born:1976});
    CREATE (Nayanthara:Person {name:'Nayanthara', born:1986});
    CREATE (Atlee:Person {name:'Atlee', born:1985});
    CREATE (ARRahman:Person {name:'AR Rahman', born:1976});
   
    
    CREATE
      (Vijay)-[:ACTED_IN {roles:['Hero']}]->(Bigil),
      (Nayanthara)-[:ACTED_IN {roles:['Heroine']}]->(Bigil),
      (Atlee)-[:DIRECTED]->(Bigil),
      (ARRahman)-[:MUSIC]->(Bigil);

     
    MATCH (m {title : "Bigil"})<-[:ACTED_IN]-(actor) RETURN actor.name;
    
    MATCH (movie:Movie {title : "Bigil"})<-[:ACTED_IN]-(actor) RETURN actor.name;


    MATCH (movie:Movie {title : "Bigil"}) RETURN ID(movie), movie;
    
    MATCH (movie:Movie) RETURN ID(movie), movie;

    MATCH (movie:Movie {title : "Asuran"}) RETURN ID(movie), movie;
    
    MATCH (movie:Movie {title : "Bigil"}) RETURN ID(movie), movie;
    
    MATCH (m {title : "Apollo 13"})<-[:ACTED_IN]-(actor) RETURN actor.name;
    MATCH (m {title : "Bigil"})<-[:ACTED_IN]-(actor) RETURN actor.name;
```




```
    CREATE (TheMatrix1:Movie {title:'The Matrix1', released:1999, tagline:'Welcome to the Real World'})
    CREATE (Keanu1:Person {name:'Keanu1 Reeves', born:1964})
    CREATE (Carrie1:Person {name:'Carrie1-Anne Moss', born:1967})
    CREATE (LillyW1:Person {name:'Lilly1 Wachowski', born:1967});
    
    CREATE
      (Keanu1)-[:ACTED_IN {roles:['Neo']}]->(TheMatrix1),
      (Carrie1)-[:ACTED_IN {roles:['Trinity']}]->(TheMatrix1),
      (LillyW1)-[:DIRECTED]->(TheMatrix1);
      
      
    MATCH (m {title : "The Matrix1"})<-[:ACTED_IN]-(actor) RETURN actor.name;  
    
    MATCH (m {title : "The Matrix1"}) RETURN m;
```





```
    CREATE (ee:Person { name: "Durai", from: "India", klout: 99 });
    CREATE (ee:Person { name: "Raja", from: "Canada", klout: 78 });
    CREATE (ee:Person { name: "Robin", from: "Sweden", klout: 89 });
    
    MATCH (ee:Person) WHERE ee.name = "Emil" RETURN ee;
    MATCH (ee:Person) WHERE ee.name = "Raja" RETURN ee;
    MATCH (ee:Person) WHERE ee.from = "Canada" RETURN ee;
    
    MATCH (ee:Person) WHERE ee.name = "Emil" RETURN ee;
    
    MATCH (ee:Person) WHERE ee.klout > 78 RETURN ID(ee), ee;
    
    MATCH (ee:Person) WHERE ee.klout > 7 RETURN ID(ee), ee;
    
    MATCH (p:Person) where ID(p) IN [1]
    OPTIONAL MATCH (p)-[r]-() //drops p's relations
    DELETE r,p;
    
    MATCH (n) DETACH DELETE n;
    
    CREATE (rj:Person { name: "Raja", from: "Canada", learn: "coding" }),
    (ro:Person { name: "Robin", from: "England", title: "developer" }),
    (su:Person { name: "Suresh", from: "India", pet: "Katie" }),
    (sa:Person { name: "Sarathy", from: "California", hobby: "reading" }),
    
    (rj)-[:KNOWS {since: 2001}]->(ro),
    (rj)-[:KNOWS {rating: 5}]->(su),
    (ro)-[:KNOWS]->(su),
    (su)-[:KNOWS]->(sa);
    
    
    MATCH (bacon:Person {name:"Raja"})-[*1..4]-(hollywood)
        RETURN DISTINCT hollywood;
```




Youtics scenarios:
```

- Dhanush is acting in a new movie which is related to Tennish. Where does he get more details in his circle?

- Santhosh Narayanan is interested to learn Golf. Who can help him out in his circle?

- Yuvan is interested in Archery. Who knows more details about Archery in his circle?
    
    
Dhanush
    title: actor
    hobbies:
    been_to: 
     
    
Santhosh Narayanan
    title: actor
    hobbies:
    been_to: canada, usa, singapore, malaysia, 
    
Yuvan
    title: actor
    hobbies: 
    been_to: canada, usa, singapore, malaysia 
```




Friends Graph:
```
- Rachel is working in a coffee shop but not good at serving right
- Chandler's parents are divorced
- Monica is a clean freak. Who is the next clean freak in the group?
- Ross is a paleontologist
- Ross lives in ?
- Ross had a crush on Rachel
- Monica's mom never appreciates her
- Monica's mom always compares Monica with Ross
- Joey Tribbiani is an actor but don't get much opportunities


// 
Person:
Monica
Rachel
Ross
Joey
Chandler
Phoebe


MATCH (n) RETURN n;

CREATE (monica:Person { name: "Monica" })
CREATE (rachel:Person { name: "Rachel" })
CREATE (ross:Person { name: "Ross" })
CREATE (joey:Person { name: "Joey" })
CREATE (chandler:Person { name: "chandler" })
CREATE (phoebe:Person { name: "Phoebe" });

MATCH (n:Person { name: 'chandler' })
SET n.name = 'Chandler'
RETURN n.name;

CREATE CONSTRAINT ON (monica:Person) ASSERT monica.name is UNIQUE

CREATE CONSTRAINT ON (rachel:Person) ASSERT rachel.name is UNIQUE;
CREATE CONSTRAINT ON (ross:Person) ASSERT ross.name is UNIQUE;
CREATE CONSTRAINT ON (joey:Person) ASSERT joey.name is UNIQUE;
CREATE CONSTRAINT ON (chandler:Person) ASSERT chandler.name is UNIQUE;
CREATE CONSTRAINT ON (phoebe:Person) ASSERT phoebe.name is UNIQUE;


// Monica Knows
MATCH (a:Person),(b:Person)
WHERE a.name = 'Monica' AND b.name = 'Rachel'
CREATE (a)-[r:KNOWS]->(b)
RETURN type(r);

MATCH (a:Person),(b:Person)
WHERE a.name = 'Monica' AND b.name = 'Ross'
CREATE (a)-[r:SIBLING]->(b)
RETURN type(r);

MATCH (a:Person),(b:Person)
WHERE a.name = 'Monica' AND b.name = 'Joey'
CREATE (a)-[r:KNOWS]->(b)
RETURN type(r);

MATCH (a:Person),(b:Person)
WHERE a.name = 'Monica' AND b.name = 'Chandler'
CREATE (a)-[r:KNOWS]->(b)
RETURN type(r);

MATCH (a:Person),(b:Person)
WHERE a.name = 'Monica' AND b.name = 'Phoebe'
CREATE (a)-[r:KNOWS]->(b)
RETURN type(r);


// Rachel Knows
MATCH (a:Person),(b:Person)
WHERE a.name = 'Rachel' AND b.name = 'Monica'
CREATE (a)-[r:KNOWS]->(b)
RETURN type(r);

MATCH (a:Person),(b:Person)
WHERE a.name = 'Rachel' AND b.name = 'Ross'
CREATE (a)-[r:SIBLING]->(b)
RETURN type(r);

MATCH (a:Person),(b:Person)
WHERE a.name = 'Rachel' AND b.name = 'Joey'
CREATE (a)-[r:KNOWS]->(b)
RETURN type(r);

MATCH (a:Person),(b:Person)
WHERE a.name = 'Rachel' AND b.name = 'Chandler'
CREATE (a)-[r:KNOWS]->(b)
RETURN type(r);

MATCH (a:Person),(b:Person)
WHERE a.name = 'Rachel' AND b.name = 'Phoebe'
CREATE (a)-[r:KNOWS]->(b)
RETURN type(r);



// Ross Knows
MATCH (a:Person),(b:Person)
WHERE a.name = 'Ross' AND b.name = 'Monica'
CREATE (a)-[r:SIBLING]->(b)
RETURN type(r);

MATCH (a:Person),(b:Person)
WHERE a.name = 'Ross' AND b.name = 'Rachel'
CREATE (a)-[r:SIBLING]->(b)
RETURN type(r);

MATCH (a:Person),(b:Person)
WHERE a.name = 'Ross' AND b.name = 'Joey'
CREATE (a)-[r:KNOWS]->(b)
RETURN type(r);

MATCH (a:Person),(b:Person)
WHERE a.name = 'Ross' AND b.name = 'Chandler'
CREATE (a)-[r:KNOWS]->(b)
RETURN type(r);

MATCH (a:Person),(b:Person)
WHERE a.name = 'Ross' AND b.name = 'Phoebe'
CREATE (a)-[r:KNOWS]->(b)
RETURN type(r);



// Joey Knows
MATCH (a:Person),(b:Person)
WHERE a.name = 'Joey' AND b.name = 'Monica'
CREATE (a)-[r:KNOWS]->(b)
RETURN type(r);

MATCH (a:Person),(b:Person)
WHERE a.name = 'Joey' AND b.name = 'Rachel'
CREATE (a)-[r:SIBLING]->(b)
RETURN type(r);

MATCH (a:Person),(b:Person)
WHERE a.name = 'Joey' AND b.name = 'Ross'
CREATE (a)-[r:KNOWS]->(b)
RETURN type(r);

MATCH (a:Person),(b:Person)
WHERE a.name = 'Joey' AND b.name = 'Chandler'
CREATE (a)-[r:KNOWS]->(b)
RETURN type(r);

MATCH (a:Person),(b:Person)
WHERE a.name = 'Joey' AND b.name = 'Phoebe'
CREATE (a)-[r:KNOWS]->(b)
RETURN type(r);



// Chandler Knows
MATCH (a:Person),(b:Person)
WHERE a.name = 'Chandler' AND b.name = 'Monica'
CREATE (a)-[r:KNOWS]->(b)
RETURN type(r);

MATCH (a:Person),(b:Person)
WHERE a.name = 'Chandler' AND b.name = 'Rachel'
CREATE (a)-[r:SIBLING]->(b)
RETURN type(r);

MATCH (a:Person),(b:Person)
WHERE a.name = 'Chandler' AND b.name = 'Ross'
CREATE (a)-[r:KNOWS]->(b)
RETURN type(r);

MATCH (a:Person),(b:Person)
WHERE a.name = 'Chandler' AND b.name = 'Joey'
CREATE (a)-[r:KNOWS]->(b)
RETURN type(r);

MATCH (a:Person),(b:Person)
WHERE a.name = 'Chandler' AND b.name = 'Phoebe'
CREATE (a)-[r:KNOWS]->(b)
RETURN type(r);




// Phoebe Knows
MATCH (a:Person),(b:Person)
WHERE a.name = 'Phoebe' AND b.name = 'Monica'
CREATE (a)-[r:KNOWS]->(b)
RETURN type(r);

MATCH (a:Person),(b:Person)
WHERE a.name = 'Phoebe' AND b.name = 'Rachel'
CREATE (a)-[r:SIBLING]->(b)
RETURN type(r);

MATCH (a:Person),(b:Person)
WHERE a.name = 'Phoebe' AND b.name = 'Ross'
CREATE (a)-[r:KNOWS]->(b)
RETURN type(r);

MATCH (a:Person),(b:Person)
WHERE a.name = 'Phoebe' AND b.name = 'Joey'
CREATE (a)-[r:KNOWS]->(b)
RETURN type(r);

MATCH (a:Person),(b:Person)
WHERE a.name = 'Phoebe' AND b.name = 'Chandler'
CREATE (a)-[r:KNOWS]->(b)
RETURN type(r);


- Monica is a chef
MERGE (a:Person {name:"Monica"})
CREATE (a)-[:WORKS]-> (:Occupation{name:"Chef"});

- Joey is an actor
MERGE (a:Person {name:"Joey"})
CREATE (a)-[:WORKS]-> (:Occupation{name:"Actor"});

- Rachel is 

-- Ross is paleontologist
MERGE (a:Person {name:"Ross"})
CREATE (a)-[:WORKS]-> (:Occupation{name:"Paleontologist"});

- Merge (Update with the existing node)
MERGE (a:Person {name:"Ann"})
CREATE (a)-[:HAS_PET]-> (:Dog{name:"Sam"})


// Joey is
// Joey works
    Actor
    Santa Claus
    Tour Guide
    Waiter
    
    MERGE (a:Person {name:"Joey"})
    CREATE (a)-[:WORKS]-> (:Occupation{name:"Santa Claus", type : "Part Time"});
    
    MERGE (a:Person {name:"Joey"})
    CREATE (a)-[:WORKS]-> (:Occupation{name:"Tour Guide", type : "Part Time"});
    
    MERGE (a:Person {name:"Joey"})
    CREATE (a)-[:WORKS]-> (:Occupation{name:"Waiter", type : "Part Time"});


// Chandler Bing
April 8, 1968
Chandler Muriel Bing
Executive

- Update Chander occupation
MERGE (a:Person {name:"Chandler"})
CREATE (a)-[:WORKS]-> (:Occupation{name:"Executive"});




// Chandler's toy
MERGE (a:Person {name:"Chandler"})
CREATE (a)-[:HAS_PET]-> (:Dog{name:"Sam"})


// Chandler has chick and duck
Chick Junior and Duck Junior
MERGE (a:Person {name:"Chandler"})
CREATE (a)-[:HAS_PET]-> (:Chick{name:"Chick Junior "});
MERGE (a:Person {name:"Chandler"})
CREATE (a)-[:HAS_PET]-> (:Duck{name:"Duck Junior"});
    
    more:
    https://www.youtube.com/watch?v=l76udM3wB4U&list=PL9Hl4pk2FsvWM9GWaguRhlCQ-pa-ERd4U&index=5
    
// DOB
Ross - October 18, 1967
MATCH (n:Person)
WHERE n.name = 'Ross'
SET n.dob = 'October 18, 1967'
RETURN n;



// Delete all relationships
start r=relationship(*) delete r;
    https://stackoverflow.com/questions/12899538/how-to-delete-all-relationships-in-neo4j-graph
    
MATCH (p:Person) RETURN p;

MATCH (p:Person) where ID(p) = 220 RETURN ID(p), p;

MATCH (n)
WHERE id(n)= 220
RETURN n;

      MATCH (p) where ID(p) = 221
      OPTIONAL MATCH (p)-[r]-() //drops p's relations
      DELETE r,p;

    // Delete all nodes
    MATCH (n) DETACH DELETE n;
    
    // Check nodes
    MATCH (n) RETURN ID(n), n;
    
    
#
Commitment-phobia meter
MATCH (n:Person)
WHERE n.name = 'Chandler'
SET n.commitment_phobia_meter = 9
RETURN n;

MATCH (n:Person)
WHERE n.name = 'Joey'
SET n.commitment_phobia_meter = 7
RETURN n;

MATCH (n:Person)
WHERE n.name = 'Ross'
SET n.commitment_phobia_meter = 1
RETURN n;

MATCH (n:Person)
WHERE n.name = 'Chandler'
RETURN n;


MATCH (p:Person)-[r]->(s:Sport)
WHERE p.name = 'Chandler'
RETURN p, s, ID(s), ID(r);



Chander plays:
    Tennis
    Racquetball
    Figure-skating
    
    MERGE (a:Person {name:"Chandler"})
    CREATE (a)-[:PLAYS]-> (s:Sport{name:"Tennis"});
    
    MERGE (a:Person {name:"Chandler"})
    CREATE (a)-[:PLAYS]-> (s:Sport{name:"Racquetball"});
    
    MERGE (a:Person {name:"Chandler"})
    CREATE (a)-[:PLAYS]-> (s:Sport{name:"Figure-skating"});
    
    
    // Clarinet
    MERGE (a:Person {name:"Chandler"})
    CREATE (a)-[:PLAYS]-> (s:MusicalInstrument{name:"Clarinet"});
    
    MATCH (p) where ID(p) in [224, 223, 220]
    OPTIONAL MATCH (p)-[r]-() //drops p's relations
    DELETE r,p;
    
Ross plays:
     basketball
     
     MERGE (a:Person {name:"Ross"})
     CREATE (a)-[:PLAYS]-> (s:Sport{name:"Basketball"});

  
Ross hates:
    Ice Cream
    
    MERGE (a:Person {name:"Ross"})
    CREATE (a)-[:HATES]-> (s:Dessert{name:"Ice Cream"});


Ross alergic
    
    Lobster, Peanuts, Kiwi
    
    MERGE (a:Person {name:"Ross"})
    CREATE (a)-[:HATES]-> (s:Food{name:"Lobster"});
    
    MERGE (a:Person {name:"Ross"})
    CREATE (a)-[:HATES]-> (s:Food{name:"Peanuts"});
    
    MERGE (a:Person {name:"Ross"})
    CREATE (a)-[:HATES]-> (s:Food{name:"Kiwi"});


Ross works
    
    Professor - New York University
    
    MERGE (a:Person {name:"Ross"})
    CREATE (a)-[:WORKS]-> (s:University{name:"New York University"});


Ross:
    SAT score 1250
    
    MERGE (a:Person {name:"Ross"})
    CREATE (a)-[:WRITES]-> (s:Exam{name:"SAT"});


Joey visits
    Los Angeles
```




Questions and Scenarios:
```
// Who is executive?
MATCH (p:Person)
WHERE (p)-[:WORKS]->(:Occupation{name:"Executive"})
RETURN p.name;


// Who is Chef?
MATCH (p:Person)
WHERE (p)-[:WORKS]->(:Occupation{name:"Chef"})
RETURN p.name;

// Get All Jobs
MATCH (o:Occupation)<-[:WORKS]-(p:Person)
RETURN p.name, o.name;

// What is Chandler's job?
MATCH (o:Occupation)<-[:WORKS]-(p:Person)
RETURN o.name;
```





```
How much money Chandler would have after 6 years?
Chandler is the wealthiest friend because he has been saving money from his job for the last six years
    Starting salary : 60k
    Yearly increase : 2%
    


Did Chandler ever eat Turkey?


Does Chandler like exercise?


Chandler is good at these games



What's his office phone number would be?


Get all of their Jobs


MATCH (n:Person)
RETURN n;


Who plays Tennis?
MATCH (p:Person)
WHERE (p)-[:PLAYS]->(:Sport{name:"Tennis"})
RETURN p.name;


Who is good at outdoor games?


Who can cook good?


Top 3 cooking persons?


Top 3 players


What are exams mentioned?
```
Sources:
https://friends.fandom.com/wiki/Rachel_Greene
https://friends.fandom.com/wiki/Chandler_Bing





```

```





```

```





```

```



### Ref :

  * [Name](file)
