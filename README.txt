ROSELN FAMILIES (family book) + ROSELN ANCESTORS (map)  -  how to put it online with Netlify
================================================================

This folder IS the website. Nothing needs to be installed or built.

FIRST TIME (about 5 minutes, free)
1. Go to https://app.netlify.com/drop and sign up (a free account; email or Google login).
2. Drag this whole "Roseln_Ancestors_App_v2" folder onto the page.
3. Netlify uploads it and gives you an address like  https://random-name-123.netlify.app
4. Rename it: Site configuration > Change site name  (e.g.  roseln-ancestors  ->  https://roseln-ancestors.netlify.app)
5. Open the address on your phone and check it, then send it to family.
   The address opens Roseln Families; the map is at the same address with /map.html on the end.
   Old links that end in #p=<number> now open that person in Roseln Families.
   Tip: to share a link that opens straight to one person, choose them in the app and copy
   the address from the browser; it ends in  #p=<their number>  (for example #p=0201.C1.8).
   A house works the same way:  #h=109  (Roseln Families) or  map.html#h=109  (the map).

OPENING IT ON YOUR OWN COMPUTER
- The two apps now load their data from the data folder, which browsers block for pages opened
  straight from a folder (file://). Use the Netlify address, or in this folder run
  "python -m http.server" and open http://localhost:8000 .

ON A PHONE
- iPhone: open the link in Safari > Share button > "Add to Home Screen".
- Android: open in Chrome > menu (three dots) > "Add to Home screen" / "Install app".
It then opens full-screen with its own church icon, and works offline after the first visit
(the village imagery and the 1869 plan are built in; live satellite detail needs a connection).

UPDATING THE SITE (important: this replaces the existing site instead of creating a new one)
1. Log in at https://app.netlify.com and click your site "roseln-ancestors".
2. Click the "Deploys" tab at the top.
3. Scroll to the bottom of the Deploys page, to the dashed box that says
   "Need to update your site? Drag and drop your site output folder here".
4. Drag this whole "Roseln_Ancestors_App_v2" folder into THAT box.
   (Dropping it on app.netlify.com/drop again makes a brand-new site with a new random address.)
5. Wait for "Published", then open https://roseln-ancestors.netlify.app and reload once or twice.
   Phones pick up the new version the next time the app is opened while online.
- The version number in sw.js (currently roseln-anc-v9) is raised each time Claude prepares an update.

PRIVACY
- The church book stops at births in 1925, so almost everyone in it has died. The only later
  entries are the family's own emigrant line (Mathilde Balthes, b.1926, d.2009).
- The app contains the whole church book (about 8,200 people), not only our direct line.
- Anyone who has the link can open it. Netlify's password protection is a paid feature; the free
  approach is simply to share the link only with family.

CREDITS
- Satellite imagery: Esri World Imagery (Esri, Maxar, Earthstar Geographics) - personal, non-commercial use.
- 1869 village plan: Christian Weiss, "Roseln mitten in Siebenbuergen" (2010), p.455.
- Family data: Ortsfamilienbuch Roseln bis 1925 (Thomas Albrich), Ortsfamilienbuch Magarei,
  Christian Weiss (book above) and Harris_Family_Tree.ged.

FILES
index.html            ROSELN FAMILIES, the main app (the site's home page). Find anyone, see their family
                      (Family / Pedigree / Descendants), one Life timeline from all the sources, each book's
                      Records and Homes, the Village (clickable 1869 plan, streets, offices) and the Books.
map.html              ROSELN ANCESTORS, the map. Opened from Roseln Families ("View on the map" on a house,
                      "Show on the map" on a person) with a "Roseln Families" button to go back.
                      Its own address:  https://<your-site>.netlify.app/map.html
families.html         forwards old links to index.html
vorfahren.html        German version of the map (Roselner Vorfahren); not yet updated.
data/people.json      the shared family data (people, homes, Weiss notes, houses, plan positions).
data/records.json     the church-book records (Roseln and Magarei), with English translations.
roseln1869.png        1869 village plan (used by both apps)
sat_*.jpg             built-in satellite images (offline fallback)
icons/                home-screen icons
manifest.webmanifest  makes Roseln Families installable (manifest-map.webmanifest does the same for the map)
sw.js                 offline support
photos/               profile photos (copies from the Ancestry tree)
family/               family photographs (Thomä and Balthes families), with captions in data/people.json
weiss/                photographs from the Weiss book that show a church-book person, a Roseln house or street,
                      or the church (captions and links are in data/people.json)
netlify.toml          Netlify settings
