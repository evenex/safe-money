# Version HEAD

* `ExchangeRate` is now a `Category`.


# Version 0.4

* BREAKING CHANGE. COMPILER WON'T COMPLAIN. HUMAN INTERVENTION POTENTIALLY
  REQUIRED. The JSON serializations for all of `Dense`, `SomeDense`, `Discrete`,
  `SomeDiscrete`, `ExchangeRate` and `SomeExchangeRate` changed. The `FromJSON`
  instances are backwards compatible with the old serializations, but the
  `ToJSON` instances will only generate the new format, which is the same as the
  old format except the leading strings `"Dense"`, `"Discrete"` and
  `"ExchangeRate"`, respectively, are not present in the rendered JSON array
  anymore. So, if you were manually relying on the `ToJSON` instance, please
  update your code.

* BREAKING CHANGE. COMPILER WILL COMPLAIN: Changed the `Rep` suffix for a `Some`
  prefix Everywhere.  For example, `DenseRep` was renamed to `SomeDense`.

* BREAKING CHANGE. COMPILER WILL COMPLAIN: Replaced the
  `someDenseAmountNumerator` and `someDenseAmountDenominator` `Integers` with a
  single `someDenseAmount` `Rational` number. Similarly for `someDiscreteScale`
  and `someExchangeRateRate`. The `mkSomeDense`, `someDiscreteScale` and
  `mkSomeDense` also take a `Rational` now.

* BREAKING CHANGE. COMPILER WILL COMPLAIN: The `truncate`, `floor`, `celing` and
  `round` functions now return just `0` as a reminder if there's no significant
  reminder, instead of `Nothing`.

* Added instances for `serialise`.

* Added instances for `xmlbf`.

* Fixed `Show` instances so that surrounding parentheses are included when
  necessary.

* New currencies: Ripple, Litecoin, Ada, Monero.


# Version 0.3

* BREAKING CHANGE: The `Data.Money` module was renamed to `Money`.

* BREAKING CHANGE: The `Data.Money.Internal` module is not exposed anymore. All
  of its contents are now exported from the `Money` module.

* BREAKING CHANGE: Renamed `discreteRep` to `toDiscreteRep`.

* BREAKING CHANGE: Renamed `denseRep` to `toDenseRep`.

* BREAKING CHANGE: Renamed `exchangeRateRep` to `toExchangeRateRep`.

* BREAKING CHANGE: Renamed Iceleandic currency `"eyir"` to `"eyrir"`

* Remove upper bound constraints from all dependencies except `base`.

* Made dependency on `store` optional for the test suite, so that it can run on
  GHCJS.


# Version 0.2

* Cabal flags are now manual (`aeson`, `binary`, `bytes`, `cereal`, `deepseq`,
  `hashable`).

* Backwards compatibility with GHC 7.10.

* Fix `Store` instances and test them.


# Version 0.1

* Initial release.
