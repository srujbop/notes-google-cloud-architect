
# Google Cloud Architect Notes

This repository contains study notes from grantcarthew (https://github.com/grantcarthew/notes-google-cloud-architect). I added my notes for studying the Google Cloud Platform to sit the Cloud Architect exam.
This repository contains my notes for studying the Google Cloud Platform to sit the Professional Cloud Architect exam.

* 2017-12-20: I passed the exam and am leaving this repository here for anyone else to use.
* 2020-02-26: Sat the exam again to maintain the certification. My certification didn't expire because of my Google Cloud Trainer certification.

__These notes have not been proof read or polished in any way. They are accurate as of June 2019.__

## Index

* [Acronyms](/Acronyms.md)
* [Build PDF](#build-pdf)
* [PDF Version](/pdf)
* [Overview](/Overview.md)
* [Courses](/Courses.md)
* [Management](/Management.md)
* [Products and Services](#products-and-services)
* [References](/References.md)
* [Study Plan](/Study%20Plan.md)

## Products and Services

* [Products and Services](Products%20and%20Services.md)
* [Big Data](/Big%20Data)
* [Cloud AI](/Cloud%20AI)
* [Compute](/Compute)
* [Design](/Design)
* [Diagrams](/Diagrams)
* [Networking](/Networking)
* [Resource Manager](/Resource%20Manager)
* [Storage](/Storage)
* [Tools](/Tools)

## Build PDF

These notes can be built into PDF (or any format for that matter) to make it easier to read and review.

There is a pre-built set of PDF documents in the [pdf](/pdf) directory.

### How to build on Windows

If you wish to build the documents yourself there is a PowerShell script in the root of the repository called [ConvertTo-PDF](/ConvertTo-PDF.ps1).

1. Install [pandoc](http://pandoc.org/) if it is not already installed.
1. Install [MikTex](https://miktex.org/) if it is not already installed.
1. Clone this repository using [git](https://git-scm.com/).
1. Open a PowerShell console.
1. Change directory to the root of the repository.
1. Run the PowerShell script by typing `.\ConvertTo-PDF.ps1`.

The script will delete the current `pdf` directory and then recreate it by building the documents from the markdown files.
Either fork this repository or raise an issue and I will make you a contributor.

__See the [Change Log](#change-log) below for update details.__

## Recommendations

Use the GitHub code view to locate documents.

I recommend installing [Octotree](https://www.octotree.io/) in [FireFox](https://addons.mozilla.org/en-US/firefox/addon/octotree/) ([why FireFox?](https://github.com/DDLSTraining/Engage/blob/master/Internet/Firefox.md)) to help you read the documents online.

Install [Mark Text (Windows)](https://marktext.app/) or [ghostwriter (Linux)](https://github.com/wereturtle/ghostwriter) to read and update the documents.

## Change Log

* 2020-02:
  * Additions:
    * Cloud Firestore
    * Cloud Dataprep
    * Cloud Data Loss Prevention
  * Updates:
    * README updated.
* 2019-10:
  * Additions:
    * Cloud Storage - Bucket Policy Only (beta)
    * Big Data - Cloud IoT Core
  * Removals:
    * PDF directory. Please build your own.
    * Diagrams Directory. Images have been integrated with the service documents.
  * Updates:
    * README updated.
* 2018-12: Contributions added
* 2018-03: Majority work completed
* 2018-02: Initial Commit
