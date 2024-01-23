# Archivarr
 An automated / self-building personal media library manager and streaming application stack


## Set-Up
1. Visit [Portainer](http://localhost:9000) to create a (local) user account
2. Go to [Deluge](http://localhost:8112) using default password 'deluge' (Change This!)
    - Set the download directories such that complete downloads go in `/downloads/complete` while incomplete downloads are written to `/downloads/incomplete`
3. Set up [Lidarr](http://localhost:8686) with similar credentials as before, you can bypass the login page from local clients by selecting the "disabled for local addresses" option at set-up
    - Under `Settings` $\rightarrow$ `Download Clients`, add Deluge using host `http://172.17.0.1:8112/` and password created previously.
    - Under `Settings` $\rightarrow$ `Media Management`, add a root folder pointing to your music library (by default this should be `/data/music`). Don't forget to check 'Rename Music' on this same page if this behavior is desired.
4. Set up [Radarr](http://localhost:7878) in a similar method as Lidarr, this time for movies.
5. Set up [Readarr](http://localhost:8787) in a similar method as Radarr, this time for books.
6. Set up [Sonarr](http://localhost:8989) in a similar method as Readarr, this time for tv.
7. Set up [Prowlarr](http://localhost:9696) as follows:
    - Under `Settings` $\rightarrow$ `Indexers` (Indexer Proxies), add Flaresolverr using host `http://172.17.0.1:8191/`
    - Under `Settings` $\rightarrow$ `Download Clients`, add Deluge using host `http://172.17.0.1:8112/` and password created previously.
    - Under `Settings` $\rightarrow$ `Apps`, add each desired application by first replacing the `localhost` with `172.17.0.1` for both entries (For example, `http://localhost:9696` becomes `http://172.17.0.1:9696/`) and inserting the applications API key found on each apps' `Settings` $\rightarrow$ `General` page.