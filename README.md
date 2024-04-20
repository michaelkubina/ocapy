<img style="float: left; margin-right: 20px;" src="ocapy/ocapy_logo.jpeg">

# OCA.py - Visualizing the word confidence of OCR results (ALTO-XML)
by Michael Kubina

**OCA.py** is an acronym and describes this **O**CR **C**onfidence **A**nalysis script written in **py**thon.

This is a graduation work for the 2022 Data Librarian Certificate Course from the Technical University Cologne. The result of the graduation work is a script, which is called OCA.py. The script was published in August 2022. This is the corresponding jupyter-notebook with additional insights.

OCA.py is licensed under GPL3 (https://www.gnu.org/licenses/gpl-3.0.en.html)

## Requirements

The following Python libraries are required:

* requests
* BeautifulSoup
* pandas
* os
* numpy
* pprint
* matplotlib
* pillow
* shutil
* seaborn

Install them with `pip install -r requirements.txt`.

This software also uses Bootstrap (https://getbootstrap.com/)

## Usage
In this graduation_work branch, the script is specifically tailored towards the METS-file-location from the Staats- und Universitätsbibliothek Hamburg. You only need to provide the record identifier in order to use it.

Examples for SUB Hamburg:
```
oca.py PPN1026788544 # about 50 pages, good ocr, low confidence
oca.py PPN86268370X  # about 150 pages, good ocr, high confidence
oca.py PPN1041860838 # about 350 pages, bad ocr -> wrong script, low confidence
oca.py PPN1672846668 # about 100 pages, bad ocr -> wrong script, extreme high confidences, visible anomaly
```

METS files from other libraries can be processed by passing the METS URL in addition to the record identifier:
```
oca.py --mets https://digi.bib.uni-mannheim.de/fileadmin/digi/1885328680/1885328680.xml PPN1885328680
```

Processing of many pages can be slow, especially if those pages also contain lots of lines and word.
On modern hardware it is possible to process several pages at the same time:
```
# Use 4 threads for parallel processing of up to 4 pages.
oca.py --thread 4 [...]
```
The number of threads won't exceed the number of total pages and
is also automatically limited to the available CPU cores.
Therefore `--threads 999` will use 100% of the available computing power.
