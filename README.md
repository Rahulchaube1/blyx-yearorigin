<img src="assets/logo.png" width="112" height="112" alt="Blyx penguin counting completed calendar years before a January bookmark.">

# YearOrigin

Count Gregorian days before January 1 of a year. This Blyx library is part of the calendar, scheduling and local time collection.

Month lengths and century leap rules affect both date validation and weekday calculations. Resolve both from the same Gregorian day number. [Python, proleptic Gregorian calendar](https://docs.python.org/3/library/calendar.html)

## Install and run

Install [Blyx 0.2.1](https://www.blyx-lang.space/download) with a Rust toolchain and host linker for native builds.

```sh
git clone --depth 1 --branch v0.1.0 https://github.com/Rahulchaube1/blyx-yearorigin.git
cd blyx-yearorigin
blyxc native-run example.blyx
blyxc native-run tests.blyx
```

[Run the editable browser example](https://www.blyx-lang.space/play?example=package-yearorigin) · [Package page](https://www.blyx-lang.space/packages/yearorigin) · [Handbook](https://doc.blyx-lang.space/guide/robin)

## Import the module

Run this in the directory containing your application's entry file.

```sh
git clone --depth 1 --branch v0.1.0 https://github.com/Rahulchaube1/blyx-yearorigin.git vendor/yearorigin
```

```blyx
use vendor::yearorigin::yearorigin;

fn main() {
    let year = 1.0;
    let result = yearorigin_offset(year);
    if len(result) == 0 { println!("invalid"); return; }
    let mut i = 0;
    while i < len(result) {
        println!(at(result, i));
        i += 1;
    }
}
```

Expected output

```text
0
0
```

## API

`yearorigin_offset(year)`

Returns [days before year, weekday of January 1]. Monday is zero; year 1 begins on Monday. Supported years are 1–9999. Invalid arguments and nonfinite results return an empty vector. Integers carried in numeric vectors use the exact range from −(2^53−1) to 2^53−1.

| Argument | Domain |
| --- | --- |
| year | A positive exact integer |

## In use

[Robin](https://github.com/Rahulchaube1/blyx-robin) uses this module to convert a validated civil date into an ordinal, weekday and comparable day number.

## Verification and contributions

The regression suite in [tests.blyx](tests.blyx) checks the example, boundary cases and invalid inputs. Include a short reproducer and your compiler version in [an issue](https://github.com/Rahulchaube1/blyx-yearorigin/issues). The source is dual-licensed under [MIT](LICENSE-MIT) or [Apache-2.0](LICENSE-APACHE). Read the [artwork notice](assets/NOTICE.txt) for credits.

## Connect with Rahul Chaube

[Portfolio](https://www.rahulchaube1.com/) · [GitHub](https://github.com/Rahulchaube1) · [LinkedIn](https://www.linkedin.com/in/rahulchaube1) · [Hugging Face](https://huggingface.co/oncody) · [X](https://x.com/RahulChaube_) · [EverestQ](https://www.everestqai.com/) · [Contact](https://www.rahulchaube1.com/contact)

[Blyx website](https://www.blyx-lang.space/) · [BlyxTorch](https://www.blyx-lang.space/packages/blyxtorch) · [Handbook](https://doc.blyx-lang.space/) · [Community](https://www.blyx-lang.space/community)

Support Rahul’s open-source work through [GitHub Sponsors](https://github.com/sponsors/Rahulchaube1) or [Buy Me a Coffee](https://buymeacoffee.com/rahulchaube).
