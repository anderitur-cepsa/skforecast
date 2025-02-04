
# Change Log
All notable changes to this project will be documented in this file.


## [0.1.9] - Unreleased

### Added

+ Logging total number of models to fit in `grid_search_forecaster()`.

### Changed

+ Argument `metric` in `cv_forecaster()`, `backtesting_forecaster()`, `grid_search_forecaster()` and `backtesting_forecaster_intervals()` changed from 'neg_mean_squared_error', 'neg_mean_absolute_error', 'neg_mean_absolute_percentage_error' to 'mean_squared_error', 'mean_absolute_error', 'mean_absolute_percentage_error'.

+ Check if srgument `metric` in `cv_forecaster()`, `backtesting_forecaster()`, `grid_search_forecaster()` and `backtesting_forecaster_intervals()` is one of 'mean_squared_error', 'mean_absolute_error', 'mean_absolute_percentage_error'.

### Fixed

+ Update lags of  `ForecasterAutoregMultiOutput` after `grid_search_forecaster()`.


## [0.1.8.1] - 2021-05-17

### Added

+ `set_out_sample_residuals()` method to store or update out of sample residuals used by `predict_interval()`.

### Changed

+ `backtesting_forecaster_intervals` and `backtesting_forecaster` print number of steps per fold.

+ Only stored up to 1000 residuals.

+ Improved verbose in `backtesting_forecaster_intervals`.

### Fixed

+ Warning of inclompleted folds when using `backtesting_forecast()` with a  `ForecasterAutoregMultiOutput`.

+ `ForecasterAutoregMultiOutput.predict()` allow exog data longer than needed (steps).

+ `backtesting_forecast()` prints correctly the number of folds when remainder observations are cero.

+ Removed named argument X in `self.regressor.predict(X)` to allow using XGBoost regressor.

+ Values stored in `self.last_window` when training `ForecasterAutoregMultiOutput`. 


## [0.1.8] - 2021-04-02

### Added

- Class `ForecasterAutoregMultiOutput.py`: forecaster with direct multi-step predictions.
- Method `ForecasterCustom.predict_interval()` and  `ForecasterAutoreg.predict_interval()`: estimate prediction interval using bootstrapping.
- `skforecast.model_selection.backtesting_forecaster_intervals()` perform backtesting and return prediction intervals.
 
### Changed

 
### Fixed


## [0.1.7] - 2021-03-19

### Added

- Class `ForecasterCustom`: same functionalities as `ForecasterAutoreg` but allows custom definition of predictors.
 
### Changed

- `grid_search forecaster()` adapted to work with objects `ForecasterCustom` in addition to `ForecasterAutoreg`.
 
### Fixed
 
 
## [0.1.6] - 2021-03-14

### Added

- Method `get_feature_importances()` to `skforecast.ForecasterAutoreg`.
- Added backtesting strategy in `grid_search_forecaster()`.
- Added `backtesting_forecast()` to `skforecast.model_selection`.
 
### Changed

- Method `create_lags()` return a matrix where the order of columns match the ascending order of lags. For example, column 0 contains the values of the minimum lag used as predictor.
- Renamed argument `X` to `last_window` in method `predict()`.
- Renamed `ts_cv_forecaster()` to `cv_forecaster()`.
 
### Fixed
 
## [0.1.4] - 2021-02-15
  
### Added

- Method `get_coef()` to `skforecast.ForecasterAutoreg`.
 
### Changed

 
### Fixed
