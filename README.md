# Rust template engine benchmarks

This repo tries to assess Rust template engine performance. Following the
download ratings from [crates.io][crates], these four projects are assessed:

- [Handlebars][handlebars]
- [Tera][tera]
- [Liquid][liquid]
- [Askama][askama]
- [horrorshow][horrorshow]
- [ructe][ructe]

[crates]: https://crates.io/categories/template-engine
[handlebars]: https://github.com/sunng87/handlebars-rust
[tera]: https://github.com/Keats/tera
[liquid]: https://github.com/cobalt-org/liquid-rust
[askama]: https://github.com/djc/askama
[ructe]: https://github.com/kaj/ructe
[horrorshow]: https://github.com/Stebalien/horrorshow-rs

## Results

As a [violin plot] generated by [Criterion]:

![Big table violin plot](big-table.svg)
![Teams violin plot](teams.svg)

[violin plot]: https://en.wikipedia.org/wiki/Violin_plot
[Criterion]: https://japaric.github.io/criterion.rs/

Numbers, as output by Criterion:

```
Big table/Askama        time:   [1.3624 ms 1.3756 ms 1.3927 ms]
Big table/Handlebars    time:   [46.968 ms 47.020 ms 47.072 ms]
Big table/Horrorshow    time:   [448.02 us 452.54 us 460.60 us]
Big table/Liquid        time:   [22.108 ms 22.154 ms 22.203 ms]
Big table/Ructe         time:   [1.6820 ms 1.6966 ms 1.7207 ms]
Big table/Tera          time:   [2.9387 ms 2.9552 ms 2.9789 ms]

Teams/Askama            time:   [1.9430 us 1.9645 us 1.9974 us]
Teams/Handlebars        time:   [27.573 us 27.756 us 28.022 us]
Teams/Horrorshow        time:   [539.74 ns 543.35 ns 549.52 ns]
Teams/Liquid            time:   [16.983 us 17.061 us 17.175 us]
Teams/Ructe             time:   [2.5024 us 2.5211 us 2.5566 us]
Teams/Tera              time:   [8.8420 us 8.9182 us 9.0320 us]
```

## Running the benchmarks

```bash
$ cargo bench
```

Plots will be rendered if `gnuplot` is installed and will be available in the
`target/criterion` folder.
