---
title: Ordering Oligos
author: Bin He
date: 2018-09-28
categories: Basics
tags: 
---

Overview
--------

We use [Benchling](https://benchling.com) to design and organize our molecular cloning projects. If you don't have an account and / or not part of the lab, please tell Bin to send you an invitation.

In Benchling, you can design primers either using the "Assembly Wizard" or "Primer Design" functions, or you can manually create or import an oligo. Either way, once you have your oligos designed and checked, you can then register it with the lab oligo database. We order our oligos from IDT through the Iowa Institute of Human Genetics. Use this [link](https://webapps1.healthcare.uiowa.edu/RAMS-DNACore/Default.aspx). If you don't have an account, either ask Bin to add you, or just give him the oligo IDs (oHXXX).

Protocol
--------

1.  Design your primers in Benchling. 
2.  If you used another tool, such as Primer 3 or Primer BLAST, please add the template as a DNA sequence into Benchling. You can then use the search function to select the primer you just designed, right click and select "create primer".
3.  Double check the sequence to make sure that you get the correct strand, and have the right amount of overhang etc.
4.  Once everything looks correct, open the oligo and navigate to "META DATA" tab. Find the "Schema" box and choose "Oligo" in the dropdown box. Fill in the project ID and any other information if you know them.
5.  Click the "Register" button on the top. In the pop out window, select "My Collection". In the "Name and Registry ID Settings", choose "Generate new registry IDs" and then click Register. 
6.  Check again to make sure everything looks correct. Now you can use the "change collection" button to register the primers into the "Organization Collection" and let the program "Generate new registry IDs". Now each oligo will get an oH number and is ready for ordering. If you don't have access to the IIHG-IDT site, stop here and give the oH# to Bin, who can order them for you. If you do have access, read on.
7.  Go to registry/Organization Collection. Restrict "type" to "Oligo" and sort by ID/reverse alphanumerical order. Use the "->" button on the left to expand the left panel. Now you can use the checkbox on the left of each oligo to select the ones you want to order. Use the export function to export the oligos to the clipboard. Paste it into Excel. We will only use the first two columns, i.e. oligo name and oligo sequence in the actual ordering step.
8.  Go to [IIHG](https://webapps1.healthcare.uiowa.edu/RAMS-DNACore/DNACore/Services/Oligo/IDT/SetupCart.aspx) oligo ordering site. Log in using your HawkID, and use the screen notification to navigate to the IDT website. Choose "Custom oligo" -> "Bulk Input" to enter your oligos. Double check and then submit.

Notes
-----

We register the oligos because this allows us to use the "Find existing primers" function in Benchling when we design new primers. Often times you will find the lab already has the primers you need. This is especially true for molecular cloning, where there are many standard parts in plasmids.

Please feel free to post comments, questions, or improvements to this protocol. Happy to have your input! Please sign your name to your note by adding '''*~~~~''': to the beginning of your tip.

References
----------

Contact
-------

-   **Bin He 12:51, 11 Oct 2018 (EDT)**
