## Publishing

To publish a version to maven repository, 
you should create a gradle.properties file in the root directory of this project.

The file is: `/path-to-project/gradle.properties`

This file is included in .gitignore file. 
You should not commit it since it contains sensitive information.

Add credentials for maven repository to `gradle.properties` file.

Example `gradle.properties` file:

```
mavenReleaseUrl=********
mavenSnapshotUrl=********
mavenUsername=************************
mavenPassword=************************
```

Then you need to invoke `release.sh` script in the project root directory.

```sh
# When the latest VERSION is 1.1.1
./release.sh patch
# New version is 1.1.2

./release.sh minor
# New version is 1.2.0

./release.sh major
# New version is 2.0.0
```

To publish a snapshot release, use `--snapshot` flag as follows:

```sh
./release.sh patch --snapshot
```

Please change the version wisely.
