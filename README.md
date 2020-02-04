Let's use [Printmaps](http://printmaps-osm.de/en/index.html) to print a nice poster (of Bern).

# Steps

1. Get the [printmaps CLI client](http://printmaps-osm.de/en/client.html) with 

```
wget http://printmaps-osm.de/files/printmaps_linux_386.tar.gz  # for Linux, get the one *you* need
tar -xvf printmaps_linux_386.tar.gz
```

2. Generate a `map.yaml` file (we like the [13th example of New York](http://printmaps-osm.de/en/beispiele.html)).
   You can either do this by issuing `./printmaps template` to create one and adapt it or by copying an example from the link above.

3. The map is then generated by subsequently calling `./printmaps create`, `./printmaps order`, `./printmaps state` and `./printmaps download`

- `./printmaps create` creates a map directory (on the server) and returns a unique map ID which is saved in the local work directory as `map.id`.
  This map ID is reused
- `./printmaps order` generates the map on the server
- `./printmaps state` returns the current map status to check for you if it's ready
- `./printmaps download` downloads (a ZIP) file of the map

4. Edit the `map.yaml` file and call `./printmaps update`, `./printmaps order`, `./printmaps state`, `./printmaps download` and `./printmaps unzip` to download and unzip an updated version.

5. Create a scale bar with `./printmaps bearingline 46.9545 7.4487 90 1000 "1 km" scalebar-1000`
