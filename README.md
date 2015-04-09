# Tabard

I was definitely not under any influence when I wrote this. At _all_.

Not-even-beta status. But it works. Kind of.

Don't use it if you're not willing to go in and figure out how the various bits function.

## Install

```
git clone https://github.com/rizqidjamaluddin/tabard.git
composer install
```

Doesn't require any database connections. It can use the default file cache fine. Make it redis if you really care, because redis is just cool like that.

Hang on, what do you mean by "tests"? I wrote this in a hurry at midnight, did you really think I thought this through? Dude, just look at all those globs and scandirs. This project probably qualifies as a weapon just because showing it to a TDD practicioner will cause them to spontaneously combust.

## Usage

Write blog posts in the `app/storage/content` folder. Name the files like `1-hello-world`, `2-bananas`, `4-watermelons` - the number at the beginning needs to be sequential, but you can skip numbers. Unix timestamps are fine. Posts will be ordered in that order. The rest of the name will be used as the URL slug. Hopefully.

Files contain a YAML metadata section up top, then markdown:

```
headline: Post Title
---

# Hello World

Normal *markdown* goes here.

```

Edit the `BlogController` and `blog.blade.php` file to fit.

Files should be regenerated by cron, updated periodically, by visiting a hidden link, or just regenerate all the time because your servers can take it, yo.
