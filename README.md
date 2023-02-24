<div align="center">
  <h1>Rust ThoughtCore</h1>

  <img alt="ThoughtAI logo source files under /logo" src="./logo/thoughtailogo.png" width="300" />

  <p>Library with support for de/serialization, parsing and executing on data-structures
    and network messages related to ThoughtCore payment chain.
  </p>
</div>

Supports (or should support)

* De/serialization of Thought protocol network messages
* De/serialization of blocks and transactions
* Script de/serialization
* Private keys and address creation, de/serialization and validation (including full BIP32 support)
* PSBT creation, manipulation, merging and finalization
* Pay-to-contract support as in Appendix A of the [Blockstream sidechains whitepaper](https://www.blockstream.com/sidechains.pdf)

For JSONRPC interaction with ThoughtCore, it is recommended to use
[rust-thoughtcore-rpc](https://github.com/philgrim2/rust-thoughtcore-rpc).

## Known limitations

### Consensus

This library **must not** be used for consensus code (i.e. fully validating
blockchain data). It technically supports doing this, but doing so is very
ill-advised because there are many deviations, known and unknown, between
this library and the ThoughtCore reference implementation. In a consensus
based cryptocurrency such as Thought it is critical that all parties are
using the same rules to validate data, and this library does not yet implement 
the same rules as Core.



### Support for 16-bit pointer sizes

16-bit pointer sizes are not supported and we can't promise they will be.
It will be dependent on rust-bitcoin implementing them first.

## Contributing

Contributions are generally welcome. If you intend to make larger changes please
discuss them in an issue before PRing them to avoid duplicate work and
architectural mismatches.

## Minimum Supported Rust Version (MSRV)

This library should always compile with any combination of features on **Rust 1.60**.

## Installing Rust

Rust can be installed using your package manager of choice or
[rustup.rs](https://rustup.rs). The former way is considered more secure since
it typically doesn't involve trust in the CA system. But you should be aware
that the version of Rust shipped by your distribution might be out of date.
Generally this isn't a problem for `rust-bitcoin` since we support much older
versions than the current stable one (see MSRV section).

## Building

The library can be built and tested using [`cargo`](https://github.com/rust-lang/cargo/):

```
git clone git@github.com:philgrim2/rust-thoughtcore.git
cd rust-thoughtcore
cargo build
```

You can run tests with:

```
cargo test
```

Please refer to the [`cargo` documentation](https://doc.rust-lang.org/stable/cargo/) for more detailed instructions.

## Release Notes

See [CHANGELOG.md](CHANGELOG.md).


## Licensing

The code in this project is licensed under the [Creative Commons CC0 1.0
Universal license](LICENSE).
