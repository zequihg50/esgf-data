---
name: ESGF Data Request Template
about: Describe the data you will download
---

**Describe the purporse of the data.**

- Who is responsible - assign the issue to that @user
- Project, paper or activity related to the data -
- Description of the project, paper or activity -
- When the data will be removed - date or `never` if it needs to be archived
- Where the data will be downloaded - for data to be `archived` pick one of the following
  - `/lustre/gmeteo/DATA/ESGF/REPLICA/DATA` (ESGF DRS compatible)
  - `/gpfs/projects/meteo/DATA/ESGF` (ESGF DRS compatible)
  - IFCA cloud (provide openstack project id)
  - Other (for data related to projects, papers or any other activity that will be removed after the end of the activity)
  - For temporal data just use your home/work directory

**Describe the data you want**

Be specific about ESGF facets, a missing facet means you are interested in all values of that facet:

- CMIP6 - project, activity_id, institution_id, source_id, experiment_id, member_id, table_id, variable_id, grid_label, frequency
- CMIP5 - project, product, institute, model, experiment, time_frequency, realm, cmor_table, ensemble, time_frequency
- CORDEX - project, product, domain, institute, driving_model, experiment, ensemble, rcm_name, rcm_version, time_frequency, variable
- Generic facets
  - latest - All ESGF versions of the dataset or only the most recent one (`true`/`false`)

For example, the following requests all members for model ACCESS-CM2 at daily resolution for two future scenarios:

```
project=CMIP6
activity_id=ScenarioMIP experiment_id=ssp370,ssp585
source_id=ACCESS-CM2
table_id=day
variable_id=tas
grid_label=fr
latest=true
```
