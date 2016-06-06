## 2.6 Facets

### 2.6.1 GET

The facet endpoint returns all facets and their corresponding ID for a given
facet type. The IDs returned from this endpoint can be used to further refine
the results returned from other endpoints.

```
facet/?type=[what|when|learn]
```


Example response

```
{​
    "Arts and Culture"​: {​
        "Carnivals"​: ​42​,
        ​"Choirs"​: ​43​,
        ​"Crafts"​: ​44​,
        ​"Eisteddfodau"​: ​45​,
        ​"Music"​: ​46​,
        ​"Operas"​: ​47​,
        ​"Theatre and performing arts"​: ​49​,
        ​"OTHER: Arts + Culture"​: ​48​
    },
    ​"Biology"​: {​
        "Animal Skins"​: ​30395​,
        ​"Birds"​: ​30397​,
        ​"Bones"​: ​30396​,
        ​"Eggs"​: ​30398​,
        ​"Flowering Plants"​: ​30399​,
        ​"Fungi/Lichens/Algae"​: ​30400​,
        ​"Insects"​: ​30401​,
        ​"Marine Invertebrates"​: ​30402​,
        ​"Non­flowering Plants"​: ​30403​,
        ​"Shells"​: ​30404​,
        ​"OTHER: Biology"​: ​30405​
    },
    ​"Community and social"​: {​
        "Agricultural societies"​: ​81​,
        ​"Clothing and accessories"​: ​52​,
        ​"Criminal System"​: ​53​,
        ​"Events"​: ​54​,
        ​"Fairs"​: ​55​,
        ​"Food & Drink"​: ​56​,
        ​"Health"​: ​57​,
        ​"Houses and Homes"​: ​58​,
        ​"Markets"​: ​59​,
        ​"People and Family"​: ​61​,
        ​"Schools / Education"​: ​62​,
        ​"Shops"​: ​63​,
        ​"Societies and clubs"​: ​64​,
        ​"OTHER: Community and Social"​: ​60​
    },
    ​"Geology"​: {​
        "Fossils"​: ​30385​,
        ​"Maps"​: ​88​,
        ​"Minerals"​: ​30386​,
        ​"Rocks"​: ​30388​,
        ​"OTHER: Geology"​: ​86​
    },
    ​"Industry and Commerce"​: {​
        "Banks / Economy / Finance"​: ​51​,
        ​"Coal"​: ​66​,
        ​"Communication and media"​: ​67​,

        "Food Industry"​: ​68​,
        ​"Industrial Disasters"​: ​69​,
        ​"Iron"​: ​70​,
        ​"Mining (Other)"​: ​71​,
        ​"Pottery"​: ​30417​,
        ​"Retail / Trade"​: ​30416​,
        ​"Slate & Lead"​: ​73​,
        ​"Steel"​: ​74​,
        ​"Tin"​: ​75​,
        ​"Trains and Railways"​: ​76​,
        ​"Transport"​: ​77​,
        ​"Waterways and Shipping"​: ​78​,
        ​"OTHER: Industry"​: ​72​,
        ​"Wool"​: ​30415​
    },
    ​"Nature Represented"​: {​
        "Scientific Illustrations"​: ​30393​,
        ​"Scientific Models"​: ​30394​
    },
    ​"Physical Environment"​: {​
        "Agricultural machinery and implements"​: ​80​,
        ​"Castles and Fortifications"​: ​30406​,
        ​"Churches, Chapels & other places of worship"​: ​30407​,
        ​"Cities, towns & villages"​: ​82​,
        ​"Farms and smallholdings"​: ​83​,
        ​"Forests/Forestry"​: ​85​,
        ​"Islands"​: ​30410​,
        ​"Landscape views"​: ​87​,
        ​"Mountains/hills"​: ​30411​,
        ​"Natural disasters"​: ​89​,
        ​"Parks and gardens"​: ​91​,
        ​"Pubs and Clubs"​: ​30412​,
        ​"Rivers, Lakes and Dams"​: ​30413​,
        ​"Seaside/Sea"​: ​30414​,
        ​"Sites, Monuments & Structures"​: ​92​,
        ​"OTHER: Physical Environment"​: ​90​
    },
    ​"Religion and Belief"​: {​
        "Christianity"​: ​94​,
        ​"Customs and practices"​: ​95​,
        ​"Nonconformist denominations"​: ​96​,
        ​"Pre Christian Wales"​: ​98​,
        ​"Religious buildings"​: ​99​,
        ​"Religious communities"​: ​100​,
        ​"Roman Catholicism"​: ​101​,
        ​"Societies and sects"​: ​102​,
        ​"World Faiths"​: ​103​,
        ​"OTHER: Religion and Beliefs"​: ​97​
    },
    ​"Sport and Leisure"​: {​
        "Clubs and societies"​: ​105​,
        ​"Fishing"​: ​84​,
        ​"Football"​: ​106​,
        ​"Holidays and resorts"​: ​107​,
        ​"Places of entertainment"​: ​109​,
        ​"Processions and public events"​: ​110​,

        "Social groups"​: ​112​,
        ​"Sports and games"​: ​113​,
        ​"Rugby"​: ​111​,
        ​"OTHER: Sport and leisure"​: ​108​
    },
    ​"War, protest and politics"​: {​
        "Civil and political rights"​: ​115​,
        ​"Elections and electioneering"​: ​116​,
        ​"First World War (1914­18)"​: ​117​,
        ​"Political parties"​: ​119​,
        ​"Second World War (1939­45)"​: ​120​,
        ​"Societies and pressure groups"​: ​121​,
        ​"Soldiers"​: ​122​,
        ​"Trade unionism & labour disputes"​: ​123​,
        ​"Warfare"​: ​124​,
        ​"OTHER: War, Protest and Politics"​: ​118​
    }
}
```