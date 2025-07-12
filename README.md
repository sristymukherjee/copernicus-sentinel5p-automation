# Automate Sentinel-5P Satellite Data download from Copernicus Data Space Ecosystem API
Automatic pipeline to download satellite data products from the Copernicus Data Space Ecosystem API.

As of November 2023, the Copernicus Open Access Hub is no longer operational. Querying products needs to be updated to work with the new Copernicus Data Space Ecosystem API. 
This Jupyter Notebook helps you automatically download Sentinel-5P data from the Copernicus Data Space Ecosystem API for your area of interest and time range.

### Prerequisites
- A [Copernicus Data Space Ecosystem account](https://identity.dataspace.copernicus.eu/auth/realms/CDSE/protocol/openid-connect/auth?client_id=account-console&redirect_uri=https%3A%2F%2Fidentity.dataspace.copernicus.eu%2Fauth%2Frealms%2FCDSE%2Faccount%2F%23%2Fpersonal-info&state=429ad7b1-20eb-4d43-97ad-3d2f4f5c30df&response_mode=fragment&response_type=code&scope=openid&nonce=389a47fd-8799-496c-8a93-60d427180edc&code_challenge=aq-4zNXzwYqxWCAdbsOb8dbct55FCaIACWLO7gFY3J4&code_challenge_method=S256)

## How to Use 
- You will need the following Python libraries:
   - pandas
   - geopandas
   - requests
   - shapely
 
You can install them with: 
pip install pandas geopandas requests shapely

- Open the tropomi_data_download.ipynb. Run it in Jupyter Notebook, JupyterLab, or VSCode
- Edit the input cells
   - Copernicus credentials: copernicus_user = "your_email"   & copernicus_password = "your_password"
   - Bounding box (area of interest): ft = "POLYGON((minLon minLat, maxLon minLat, maxLon maxLat, minLon maxLat, minLon minLat))"
     Example for South Asia: POLYGON((60.899437 5.918472, 100.415291 5.918472, 100.415291 38.078327, 60.899437 38.078327, 60.899437 5.918472))
   - Date range:   start_date = "YYYY-MM-DD"  &  end_date = "YYYY-MM-DD"
   - Save directory: save_dir = "path/to/your/folder"
 
## Notes 

- If a file fails to download, its name will be saved in failed_downloads.txt in your output folder.

- If you stop the download midway, you can re-run the script with the same settings. It will pick up where it left off.

- You can modify the script to download other Sentinel data by adjusting the data_collection and product settings.

---

Feel free to fork this repo, suggest improvements, or adapt it for your own research.
  
