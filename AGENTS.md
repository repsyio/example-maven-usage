# AGENTS.md

Sample that uses a library from a Repsy Maven repository with Maven, configured through `~/.m2/settings.xml`.

Sibling samples: `example-gradle-deploy`, `example-gradle-usage`, `example-maven-deploy`, `example-maven-usage`
(the `*-usage` samples consume what the matching `*-deploy` sample publishes, group `io.repsy.example`, version 1.0).
They back articles on https://docs.repsy.io; they are not Repsy product code, so the Repsy Jira and PR rules do not apply.

## Layout
- `pom.xml`: `io.repsy.example:maven-usage:1.0`, Java 1.8, repository id `repsy` (placeholder URL `https://repo.repsy.io/mvn/myuser/default`), dependency `io.repsy.example:maven-deploy:1.0`.
- `src/main/java/io/repsy/example/maven_usage/Main.java`; `mvnw`: Maven wrapper.

## Commands
- Build: `./mvnw package`; resolving the dependency needs the deploy sample published and `repsy` credentials in `~/.m2/settings.xml` (do not run unasked). No tests or CI.
- The wrapper pins Maven 3.6.0 (`.mvn/wrapper/maven-wrapper.properties`); `./mvnw package` is unverified here and may fail with the current compiler plugin.

## Conventions
- Default branch `master`. Few commits; titles are short free-form sentences, no ticket prefix; squash merges add ` (#N)`.
- `.github/dependabot.yml` exists (Dependabot only, no CI).
- Keep the sample minimal and in line with the docs article linked in `README.md`.
- Never put real credentials or a real username in the files; the Repsy URL and credentials are placeholders or properties.
