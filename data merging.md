SCALANIE DANYCH / DATA MERGING

**PL:** Ze względu na limity rozmiaru plików na GitHub (>100MB), główne zbiory danych (.csv) zostały podzielone na mniejsze części. Aby odtworzyć pełne bazy danych lokalnie, należy wykonać poniższe komendy w głównym folderze projektu:

**EN:** Due to GitHub file size limits (>100MB), the primary datasets (.csv) have been split into smaller parts. To reconstruct the full datasets locally, run the following commands in the project root folder:

### Windows (Command Prompt / CMD):
copy /b crime_part_aa + crime_part_ab + crime_part_ac + crime_part_ad + crime_part_ae + crime_part_af + crime_part_ag + crime_part_ah crime-data-from-2010-to-present.csv
copy /b arrest_part_aa + arrest_part_ab + arrest_part_ac + arrest_part_ad arrest_data-from-2010-to-present.csv
### macOS / Linux (Terminal):
cat crime_part_* > crime-data-from-2010-to-present.csv
cat arrest_part_* > arrest_data-from-2010-to-present.csv
