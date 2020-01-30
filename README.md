# Mel Specification

## Contents

## Overview

Mel is a software that allows playback, organization, streaming and distributing
of music files. Users can organize not only music that is locally stored on the
device they are using, but also from any device connected. Furthermore they can
playback the music on any connected playback device.

### Main Components

There are three main components that are used to build Mel Instances. For each of
them, there is a specification for its programming API and REST API. Here is an
overview for each of them:

The [**Mel Music Database**](#mel-music-database) stores all information about tracks that are available
locally as a audio file or remotely as a stream.

- _Meta data_, such as artist name, album title, release year and track title
- _The Generic Music Identifier (GMID)_ that uniquely identifies a track across
  all instances of Mel
- _Source information_, which contains information on possible sources for the
  actual sound data, like local music files or remote stream capabilities and its
  quality

The **Mel User Database** stores user data and user generated data.

- _Authentication information_ like username, password and e-mail
- _Personalized information_ like displayed name and avatar image
- _Playlists_ which include a title, thumb image and an ordered list of GMIDs

The **Mel Playback Agent**

There are two types of Mel Users:  
**Registered Mel Users** are registered at a specific Mel Instance and can be
identified using the &lt;username&gt;@&lt;domain&gt; scheme, where _domain_ is the domain of
the users User Host Instance. All user data of Registered Mel Users is
synchronized with its User Host Instance once connecting to it is possible.  
**Unregistered Mel Users** are local users that do not synchronize data with
other Mel Instances. They can be upgraded to a Registered Mel Users, which will
merge data with the existing user.

## Mel Music Database

### Properties

A **Unique Database ID** is generated when the database first initializes. It
is a UUIDv1, so the it can be uniquely identified across multiple Mel Instances.

The **Database Name** helps users to identify different Music Database more
easily.

### Used datasets

- [**Music Database**](#music-database)
- [**File Source**](#file-source)
- [**Stream Source**](#stream-source)
- [**Track**](#track)
- [**Album**](#album)
- [**Artist**](#artist)

### Programming API

#### General

##### Read Database ID

Returns the unique database ID of the current instance.

_Return value_: Database ID

##### Read Database Name

Return the name of the current database instance.

_Return value_: Database Name

##### Update Database Name

Changes the current databases name.

_Parameters_:

- _name_ - the new name the current database is supposed to have.

##### Read Database Logo

##### Update Database Logo

### Tracks

##### Create Track

Creates a new track entry based on the provided Track data.

_Parameters_:

- _Track dataset_ - the track to create

##### Read Track

Reads a tracks meta data by Track GMID.

_Parameters_:

- _Track GMID_ - the GMID of the track to read

_Return value_: Track dataset

##### Update Track

Updates a Track dataset by Track GMID.

_Parameters_:

- _Track GMID_ - the GMID of the track to update
- _Track dataset_ - the dataset to update to current with

##### Delete Track

Deletes a track by Track GMID.

_Parameters_:

- _Track GMID_ - GMID of the track to delete

##### Find Tracks-

#### Albums

#### Artists

#### Sources

#### Music Databases

#### User Permissions

### REST API

## Datasets

##### Music Database

- _host_
- _name_
- _logo_
- _id_

##### File Source

- _track GMID_
- _file path_
- _format_
- _bitrate_

##### Stream Source

- _track GMID_
- _available bitrates_
- _remote track database id_

##### Track

- _GMID_
- _title_
- _album GMID_
- _number_
- _tags_
- _featured artist GMID_

##### Album

- _GMID_
- _title_
- _artist GMID_
- _tags_

##### Artist

- _GMID_
- _name_
- _tags_

## Glossary

##### Mel Instance
Software that implements at least one of the three main components of Mel and 
exposes a Mel Api of at least one of them.

##### User Host Instance
A Mel Instance, which implements the Mel User Database and its REST API.

##### Music Host Instance
A Mel Instance, which implements the Mel Music Database and its REST API.

##### Generic Music Identifier
An ID that is generated from a tracks essential meta data. 
See [GMID Generator](https://github.com/FritzHeiden/gmid-generator)

# Acronyms

**GMID** - Generic Music Identifier
