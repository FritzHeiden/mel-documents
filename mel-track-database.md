# Mel Track Database

## Datasets

**Remote Track Database**

- _host_
- _name_
- _logo_
- _id_

**File Source**

- _track GMID_
- _file path_
- _format_
- _bitrate_

**Stream Source**

- _track GMID_
- _available bitrates_
- _remote track database id_

**Track**

- _GMID_
- _title_
- _album GMID_
- _number_
- _tags_

## Programming API

### General

**Read Database ID**

**Read Database Name**

**Update Database Name**

**Read Database Logo**

**Update Database Logo**

### Tracks

**Create Track** - creates a new track entry based on the provided Track data.
Parameters:

- _Track dataset_ - the track to create

**Read Track** - reads a tracks meta data by Track GMID.
Parameters:

- _Track GMID_ - the GMID of the track to read

Return value: Track dataset

**Update Track** - updates a Track dataset by Track GMID.
Parameters:

- _Track GMID_ - the GMID of the track to update
- _Track dataset_ - the dataset to update to current with

**Delete Track** - deletes a track by Track GMID.
Parameters:

- _Track GMID_ - GMID of the track to delete

**Find Tracks** -

### Albums

### Artists

### Sources

### Remote Track Databases

## REST API
