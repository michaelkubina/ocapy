<img style="float: left; margin-right: 20px;" src="ocapy/ocapy_logo.jpeg">

# OCA.py - Visualizing the word confidence of OCR results (ALTO-XML)
by Michael Kubina

**OCA.py** is an acronym and describes this **O**CR **C**onfidence **A**nalysis script written in **py**thon.

This is a graduation work for the 2022 Data Librarian Certificate Course from the Technical University Cologne. The result of the graduation work is a script, which is called OCA.py. The script was published in August 2022. This is the corresponding jupyter-notebook with additional insights.

OCA.py is licensed under GPL3 (https://www.gnu.org/licenses/gpl-3.0.en.html)

## Requirements

The following python-libraries are required.

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

This software also uses Bootstrap (https://getbootstrap.com/)

## Usage
In this graduation_work branch, the script is specifically tailored towards the METS-file-location from the Staats- und Universitätsbibliothek Hamburg. You only need to provide the record identifier in order to use it. This also means, that you can currently just test it on objects from this specific library. For other METS-files a refactoring is necessary.