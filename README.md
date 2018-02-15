# [Montreal Forced Aligner] release assets

## What?

This provides the release assets for the [Montreal Forced Aligner] in resolvable form.
[Tags in this repository] are [Ivy] repositories containing those release assets.

## Why?
 
This construct makes it possible to resolve the release assets from GitHub through the [RawGit] CDN without getting a `403 Forbidden` HTTP response or similar. 
It's a workaround for limitations in [Gradle]'s dependency resolution engine.

## How?

In your [Gradle] project, declare a custom Ivy repository, (optionally) a custom configuration, and one or more dependencies on a [Montreal Forced Aligner] release asset like this:

```groovy
repositories {
    ivy {
        url 'https://cdn.rawgit.com/marytts/montreal-forced-aligner-release-assets/1.0.0'
    }
}

configurations {
    mfa
}

dependencies {
    mfa group: 'com.github.montrealcorpustools', name: 'montreal-forced-aligner', version: '1.0.0', classifier: 'linux', ext: 'tar.gz'
    mfa group: 'com.github.montrealcorpustools', name: 'montreal-forced-aligner', version: '1.0.0', classifier: 'macosx', ext: 'zip'
    mfa group: 'com.github.montrealcorpustools', name: 'montreal-forced-aligner', version: '1.0.0', classifier: 'win64', ext: 'zip'
}
```

[Gradle]: https://gradle.org/
[Ivy]: http://ant.apache.org/ivy/
[Montreal Forced Aligner]: https://github.com/MontrealCorpusTools/Montreal-Forced-Aligner
[RawGit]: http://rawgit.com/
[Tags in this repository]: https://github.com/marytts/montreal-forced-aligner-release-assets/tags
