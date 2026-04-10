
# Wetland Field App PWA

GitHub-ready Progressive Web App for offline-capable wetland field collection.

## Upload to GitHub
1. Create a new repository on GitHub.
2. Upload every file and folder from this package.
3. Go to **Settings > Pages**.
4. Choose **Deploy from a branch**.
5. Choose the `main` branch and `/ (root)`.
6. Open the published Pages URL in Safari on iPhone.
7. Use **Share > Add to Home Screen**.

## Includes
- Start screen: New Project Folder / Open Existing Project
- Region templates:
  - Atlantic & Gulf Coastal Plain (ENG 6116-2)
  - Great Plains (ENG 6116-5)
  - Arid West (ENG 6116-1)
- Separate vegetation stratum tables
- 50/20 dominance test by stratum
- Prevalence index
- Soil triggers with reasons
- Hydrology logic
- Save locally
- Export CSV
- Export regional JSON

## Important limitations
- A web app on iPhone cannot directly manage Bluetooth GNSS through Web Bluetooth in Safari on iOS.
- Browser cache/storage is strong but not guaranteed permanent forever.
- MLRA/LRR and soil map unit are left blank unless you later import or connect an API.

## Replace the plant list later
Replace `data/plants.json` with the official uploaded list using this structure:
```json
{
  "scientificName": "Typha latifolia",
  "officialCommonName": "Broadleaf cattail",
  "altCommonNames": ["Common cattail", "Cattail"],
  "indicatorStatusByRegion": {"AGCP":"OBL","GP":"OBL","AW":"OBL"}
}
```


## Updated Plant List
This package now includes the 2022 NWPL national workbook reduced to the fields used by the app for AGCP, GP, and AW.


## In-app project folder workflow
This version uses an in-app project folder concept based on the project name.
- Each project acts like its own folder inside the app.
- After each data point is calculated/saved, the app automatically prepares a CSV copy for that point in local app storage.
- Use **Save Current Point CSV to Files** to push that specific point's CSV into the iPhone Files share/save sheet.
- File names are prefixed with the project folder name, for example:
  `My_Project__DP-01.csv`

This is the closest reliable iPhone web-app workflow to automatic foldered CSV output without a native app.
