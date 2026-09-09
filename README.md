# Badanie-Kataster

Dane na temat lokalizacji metra zostały pobrane ze strony: https://overpass-turbo.eu

Zostały wywołane kodem: 
[out:csv(::type, ::id, name, "railway:ref", colour, start_date, ::lat, ::lon; true; "|")][timeout:60];
area["name"="Warszawa"]["admin_level"="6"]->.a;
node["station"="subway"]["railway"="station"]
    [!"construction"][!"proposed"]
    ["disused"!~"."]["abandoned"!~"."](area.a);
out;
