GitHub & Travis Docker-based Build & Deploy Integration
---

[![GitHub release](https://img.shields.io/github/release/hadisfr/travis-test.svg?style=flat-square)](https://github.com/hadisfr/travis-test/releases/latest)
[![Travis (.com)](https://img.shields.io/travis/com/hadisfr/travis-test.svg?style=flat-square)](https://travis-ci.com/hadisfr/travis-test)

Use `-v` or `--volume` flag in docker run to to bind mount a volume,
and `-w` or `--workdir` flag to set working directory.

Use the following command to generate `api_key`:
```bash
travis setup releases --com
```
Previous access toknes are available at https://github.com/settings/tokens.

Add the following parts to `deploy` section of `.travis.yml`:
```yml
deploy:
  provider: releases
  file_glob: true
  skip_cleanup: true
  on:
    tags: true
```

## References

* https://www.victorhurdugaci.com/github-releases-travis
* https://github.com/harshjv/travis-ci-latex-pdf/blob/master/.travis.yml
* https://docs.travis-ci.com/user/languages/minimal-and-generic
* https://docs.travis-ci.com/user/deployment/releases
