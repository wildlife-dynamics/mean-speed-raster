# mean-speed-raster

mean-speed-raster

## What it does

| Step | What it does |
|---|---|
| **Connect to Earthranger** |  |
| **Set Base Maps** |  |
| **Set Workflow Details** | Add information that will help to differentiate this workflow from another. |
| **Set Time Range** | Choose the period of time to analyze. |
| **Set Groupers** |  |
| **Subject Group** | Get observations for a subject group from EarthRanger. |
| **Process Relocs** |  |
| **Trajectory Segment Filter** |  |
| **Add Temporal Index** |  |
| **Map Columns** | Maps and transforms the columns of a DataFrame based on the provided parameters. The order of the operations is as follows: drop columns, retain/reorder columns, and rename columns. |
| **Split Groups** |  |
| **Build Ecograph** | Build an Ecograph from trajectory data and return one movement covariate or network metric as a GeoDataFrame of raster-cell polygons. |
| **Apply Classification** | Classifies a dataframe column using specified classification scheme. |
| **Apply Color Map** | Adds a color column to the dataframe based on the categorical values in the specified column. |
| **Create Geojson Layer** | Creates a GeoJSON layer definition based on the provided configuration. |
| **Compute View State From Gdf** |  |
| **Persist Ecograph** | Persist dataframe to a file or cloud storage object. |
| **Create Files Single View** | Create the files associated with a single view. |
| **Persist Relocations** | Persist dataframe to a file or cloud storage object. |
| **Persist Trajectories** | Persist dataframe to a file or cloud storage object. |
| **Draw Ecograph Map** | Creates a map based on the provided layer definitions and configuration. |
| **Persist Ecograph Map** | Persist text to a file or cloud storage object. |
| **Create Ecograph Widget Single View** | Create a map widget with a single view. |
| **Merge Widget Views** | Merge widgets with the same `title` and `widget_type`. |
| **Gather Dashboard** |  |

## Requirements

- Access to a **EarthRanger** data source, set up as a connection

---

## 1. Load the Workflow

In the workflow runner, add a new template using this repository's URL. Once added, select
**mean-speed-raster** from the available templates list to load it.

---

## 2. Configure the Workflow

You'll be prompted to fill in the following parameters before running.

### Connect to Earthranger

| Field | Description | Default |
|---|---|---|
| Data source *(required)* | Select one of your configured data sources. | — |

### Set Workflow Details

| Field | Description | Default |
|---|---|---|
| Workflow Name *(required)* |  | — |
| Workflow Description |  | `` |

### Set Time Range

| Field | Description | Default |
|---|---|---|
| Since *(required)* | The start time | — |
| Until *(required)* | The end time | — |
| Timezone |  | — |

### Subject Group

| Field | Description | Default |
|---|---|---|
| Subject Group Name *(required)* | ⚠️ The use of a group with mixed subtypes could lead to unexpected results | — |

### Build Ecograph

| Field | Description | Default |
|---|---|---|
| Cutoff | Cutoff distance for kernel. | — |
| Step Length | Mean step length, used as the resolution if `resolution` is None. | `2000` |

---

## Developing

```bash
# recompile spec.yaml (first time: --install; after that: --update, which bumps VERSION.yaml)
./dev/recompile.sh --update

# run the test cases in test-cases.yaml
pixi run --manifest-path pixi.toml -e default bash dev/pytest-cli.sh mean_speed_raster --all
```

Documentation: [docs/index.html](docs/index.html).
