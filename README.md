# New York City Elevators

A list of registered elevator devices in New York City provided by the Department of Buildings in response to a September 2015 FOIL request.  The data was received on a DVD in November 2015.  The spreadsheet contains information on 76,088 elevators in New York City.

`Elevator Data.xlsx` is the original file received from the New York City Department of Buildings.

`elevators.csv` is the same file converted to CSV, with some broken contents repaired.  It has two additional columns: `LATITUDE` and `LONGITUDE`.  These numbers should NOT be considered authoritative, they are approximations obtained by geocoding the BIN, the Borough+Block+Lot, or the street address through the [New York City Geoclient API](https://developer.cityofnewyork.us/api/geoclient-api).  Some geocoding results may be in error.

Information about an individual elevator device can also be obtained from the NYC Department of Buildings [Building Information Search](http://a810-bisweb.nyc.gov/bisweb/bispi00.jsp), by entering a device number in the Elevator Device Search (Field 26).

## Notes

* Several columns have inconsistent data.  For example, `DV_TRAVEL_DISTANCE` is often omitted, and when it's provided, the units and format vary. Use with caution.
* The spreadsheet contains at least seven rows of dummy test data (identifiable by the street name `DUMMY RECORD`).
* The street address is for the "Filed At" address, which may be different from the actual premises of the device.  The BIN or the Borough+Block+Lot is generally more accurate for geolocation.
* `ZIP_CODE` is frequently listed as a nine-digit ZIP+4.
* Dates are listed in the format `YYYYMMDD`.
* The column `DV_LASTPER_INSP_DATE` refers to the last periodic inspection by the Department of Buildings.  Because this data is several months old, some of these dates will no longer be accurate.
* The file was converted to CSV using `in2csv --no-inference Elevator\ Data.xlsx > elevators.csv`. In the original Excel file, a small number of device numbers were originally formatted as numbers in scientific notation instead of text (e.g. the device number `1E217` became  `1.00E+217`). These have been manually repaired.
