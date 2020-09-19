# TO-DOs for TROCAS Data Browser App

Updated 2020-9-19

- Priority Panel widget and annotation development
  - Add a text display of the date-time start and end for the selected TROCAS. Later, could enhance this by showing start - end of GPS-merged binned data vs start-end of all data, regardless of GPS match
  - Add text input boxes to manually set the parameter value min and max, with a toggle (checkbox) to switch from fixed (global values) to manually set.
  - Add a third histogram overlay, showing the histogram for the data in the current geographical extent? It'd be helpful, but likely too crowded.
  - Choice of `mainmap.opts` `width` & `height` vs `frame_width` and `frame_height` has consequences on both the space the map occupies and how and when it rearranges itself horizontally when zooming in (when y tick labels add/drop a digit) or changing parameters (and the colorbar legend values add/drop digits)
  - Add a colorbar legend/label. *But a vertical label doesn't appear to be currently doable. See [here](https://discourse.holoviz.org/t/how-to-specify-a-vertical-colorbar-label/444) and [here](https://stackoverflow.com/questions/46841919/bokeh-colorbar-vertical-title-to-right-of-colorbar).*
- `mbdata_dielcoll_df` `agg_dct` operations
  - Add min & max (or 1 stdev) to longitude and latitude agg, to help assess what's being averaged, whether it really is a tightly clustered set of points. But will then need to use the scheme to simplify multi-level columns to single-level column names (eg, longitude_min, longitude_mean)
  - Including `date_time` in `agg_dct` results in an error. Investigate it.
- Add Conductivity; it's missing from `merged_1minbinned_df.parq`.
- Add a small map (lower right) visually indicating the earliest (eg, dark) vs later (light) sampling dates for the TROCAS.
- Problems I was seeing with chlorophyll, isotopes, etc, all apparently had to do with **negative values with a log scale** (`logz=True`)! I'll need to implement log scaling as an option (checkbox), that maybe is only available for a pre-defined set of parameters.
- *(Partially done).* Add global min-max range to each parameter. Then add capability to plot using global, fixed min-max, while also allowing a floating, self-scalable range (what's currently happening by default)
- 2020-9-13: *(Working on it, but it looks like it won't be possible).* Replace use of geoviews with functionality from holoviews and datashader; see block of code below

## Completed

- 2020-9-19: Enable synchronization between the map color range limits and the histogram x-axis range.
- 2020-9-17: Set the y-axis tick labels in the histogram plot to scientific notation, so that the app layout is not shifted (it's jarring) when the parameter is changed
- 2020-9-15: Move all the data-loading and pre-processing code to a module ("Load and pre-process Binned-Merged data", "Diel stations" and "Sensor inventory" sections).
- 2020-9-13: Enable switching basemap bewtween the ESRI World Terrain currently used, and Satellite.
