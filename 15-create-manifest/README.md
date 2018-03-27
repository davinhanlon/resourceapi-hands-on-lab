# Create Manifest

TODO: write this and check that it works

cd to the Manifests directory

Create a file name ```somemanifest.pp``` with the following content

```
temp { 'stattemperature':
  ensure => present,
  temp   => 24,
}
```
