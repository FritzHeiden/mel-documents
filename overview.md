# Overview

Mel is a software that allows playback, organization, streaming and distributing
of music files. Users can organize not only music that is locally stored on the
device they are using, but also from any device connected. Furthermore they can
playback the music on any connected playback device.

## Main Components

There are 3 main components that are used to build Mel instances. For each of
them, there is a specification for its programming API and REST API. Here is an
overview for each of them:

The **Mel Track Database** stores all information about tracks that are available
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
identified using the <username>@<domain> scheme, where _domain_ is the domain of 
the users User Host Instance. All user data of Registered Mel Users is 
synchronized with its User Host Instance once connecting to it is possible.
**Unregistered Mel Users**

# Glossary

**Mel instance** - Software that implements at least one of the three main
components of Mel and exposes a Mel Api of at least one of them.
**User Host Instance** - A Mel Instance, which implements the Mel User Database 
and its REST API.
**Generic Music Identifier** - An ID that is generated from a tracks essential
meta data. See [GMID Generator](https://github.com/FritzHeiden/gmid-generator)

# Acronyms

**GMID** - Generic Music Identifier
