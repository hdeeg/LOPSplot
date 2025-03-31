# LOPSplot
(this is a private branch from https://github.com/PLATO-DLR/plato_utilities/tree/main/src/plato_utilities/LOPSplot )

Simple plotter for targets in PLATO fields: 
- From an input list, selects targets within the PLATO LOPS2 field 
- Plots the targets in LOPS2, in galactic and equatorial coordinates
- Saves the list of targets within LOPS2

Besides the notebook, provided are a fits.gz file with the description of LOPS2 in terms of the number of cameras (6,12,18 or 24), and an example input-list (RV standards from Soubiran+2013, downloaded from Vizier).
 
Comments:
- The full list of input targets can be plotted by setting 'LOPSonly=False' (near the center of the NB)

- The selection of the targets is made in galactic coordinates against the LOPS2 field representation (the fits.gz file). This is due to the fits.gz's coordinates being defined in galactic ones.

- The projections are done using the nominal coordinates for first field to be observed by PLATO for at least two continuous years: LOPS2. The details about the coordinates can be found in Nascimbeni et al. (2025) A&A, 694, A313. 
 
- The plot in l,b provides a precise overlay between targets and the LOPS2 field-representation, whereas the one in RA-Dec may show discrepancies of up to ~2 degree between targets and the edges of LOPS2. This is due to unresolved projection issues of LOPS2; the targets are plotted at correct positions. There should be better ways to plot LOPS2; for potential alternatives, see Appendix A in Nascimbeni et al. 2025.

- 3 columns describing the nominal, minimal and maximal number of cameras for a given target are added to the output-list.
 
- The targets are selected by testing against the nominal number of cameras (n_nom). If the selection of all potential targets is desired, testing against n_max is advised; whereas testing against n_min provides higher (but not 100%) security that a target will be in LOPS2. Full security that a target near the edges will fall into LOPS2 will only be achieved once the mission is in orbit!

- The code also generates (but does not use) an 'edgeID' that indicates if a target is at the field-edge.
 
- The core-part of the code (target-selection, galactic plot) is from nplatocam.py at https://github.com/PLATO-DLR/plato_utilities, written by Pierre Maxted. The fits file nplatocamLOPS2_2.fits.gz is based on nplatocamLOPS2.fits.gz in the same repository. This is a non-public site, for access contact Juan Cabrera at DLR (Juan.Cabrera@dlr.de).

- The notebook was developed with: python 3.12.2, astropy 7.0.0, scipy 1.13.0, numpy 1.26.4 
