<h1 align=center>Dockette / Upstream</h1>

<p align=center>
   <a href="https://github.com/sponsors/f3l1x"><img src="https://img.shields.io/badge/sponsor-GitHub%20Sponsors-ea4aaa" alt="GitHub Sponsors"></a>
   <a href="https://github.com/orgs/dockette/discussions"><img src="https://img.shields.io/badge/support-discussions-6f42c1" alt="Support/Discussions"></a>
</p>

<p align=center>
   🎁 Legacy PHP CLI images with Composer in Docker
</p>

-----

> [!WARNING]
> **Deprecated.** These Dockerfiles are no longer maintained, and the repository is archived. They are based on the
> official `php` Alpine images for PHP 5.6, 7.0 and 7.1, which are end-of-life, and no image is published on Docker Hub.
> Use the official [`php`](https://hub.docker.com/_/php) images instead.

Dockerfiles for PHP `5.6`, `7.0` and `7.1` CLI on the official `php:<version>-alpine` base.

## What is inside

- PHP extensions `bcmath`, `calendar`, `pdo`, `pdo_mysql` and `xml`
- [Composer](https://getcomposer.org) with `hirak/prestissimo`
- custom `php.ini` overrides in `php/<version>/conf.d/custom.ini` (memory and upload limits, timezone `Europe/Prague`)
- working directory `/srv`, default command `php`

## Usage

```sh
docker build -t upstream-php php/7.1
docker run -it --rm -v $(pwd):/srv upstream-php php -v
```

## Maintenance

See [how to contribute](https://github.com/dockette/.github/blob/master/CONTRIBUTING.md) to this package. Consider to
[support](https://github.com/sponsors/f3l1x) **f3l1x**. Thank you for using this package.
