# Releasing

1. Change the version in top-level `gradle.properties` to a non-SNAPSHOT version.
2. Update the `CHANGELOG.md` for the impending release.
3. Update the `README.md` with the new version.
4. `git commit -am "Prepare for release X.Y.Z."` (where X.Y.Z is the new version).
5. `./gradlew publishAllPublicationsToMavenCentral`
6. Visit [Sonatype Nexus](https://s01.oss.sonatype.org/) to verify the release has been completed.
7. `git tag -a X.Y.X -m "X.Y.Z"` (where X.Y.Z is the new version)
8. Update the top-level `gradle.properties` to the next SNAPSHOT version.
9. `git commit -am "Prepare next development version."`
10. `git push && git push --tags`

If step 5 or 6 fails, drop the Sonatype repo, fix the problem, commit, and start again at step 5.
