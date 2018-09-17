# [Montreal Forced Aligner] release assets

## What?

This provides the release assets for the [Montreal Forced Aligner] in resolvable form.
[Tags in this repository] contain those release assets.

## Why?
 
This construct makes it possible to resolve the release assets from GitHub as "source code" downloads without getting a `403 Forbidden` HTTP response or similar. 
It's a workaround for limitations in [Gradle]'s dependency resolution engine.

## How?

In your [Gradle] project, declare a custom Ivy repository, (optionally) a custom configuration, and one or more dependencies on a [Montreal Forced Aligner] release asset like this:

```groovy
repositories {
    ivy {
        url 'https://github.com/marytts/montreal-forced-aligner-release-assets/archive'
        layout 'pattern', {
            artifact '[revision]-[classifier].[ext]'
        }
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
