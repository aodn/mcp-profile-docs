.. _introduction:

Introduction
============

.. index:: type 1 and type 2 profiles of ISO19115

The MCP is a `type 2` profile of :term:`ISO19115` implemented in :term:`XML` using :term:`ISO19139`. This means that:

#. Any element of ISO19115 can be used in the MCP
#. New elements have been added using the approved extension procedures for ISO19115 and the XML implementation of ISO19139
#. Controlled vocabularies for certain metadata elements (also known as code lists) and rules for validating metadata records from ISO19115 have been extended and new controlled vocabularies and rules for checking validity have been added

`Type 1` profiles of :term:`ISO19115` are simpler than `type 2` profiles because they do not add new elements. Examples of `type 1` profiles are the ANZLIC Metadata profile and the WMO (World Meteorological Organisation) profile version 1.2.

XML Fragments
-------------

This manual uses fragments of XML to describe the MCP. Some familiarity with the following XML concepts is required:

- namespaces
- elements and attributes
- schemas

The basic concepts and ideas behind XML can be found at http://www.w3schools.com/xml and other places on the internet. 

For brevity and to help understanding, fragments of XML will be written as follows:

- using a different font and background
- indented where possible to help reading 
- where an XML element, including the start tag, end tag and content, is too long to show on a single line, it shall break across more than one line automatically
- content not relevant to the purpose of the fragment will be replaced by an ellipsis (...)

XML Conventions
---------------

These conventions reuse and extend the conventions set out in the 
`WMO Core Metadata Profile v1-2 Manual <http://wis.wmo.int/2010/metadata/version_1-2/>`_ by Jeremy Tandy. The conventions are as follows:

- The schema documents (see :term:`XSD`) and codelists for the Marine Community Profile extend those used for ISO19139 and ISO19136. They are available online at http://bluenet3.antcrc.utas.edu.au/mcp-1.4.
- The schema documents for ISO19139 are included with the MCP schema documents. They are also available from the `ISO TC211 website <http:///www.isotc211.org/2005>`_ (see also :term:`ISO TC211`). 
- A number of different namespaces are used to separate metadata elements into packages for easier management or to include XML implementations of other standards such as GML. The result is that an MCP metadata record will incorporate multiple namespaces as follows:

 - The namespace identifier for mcp shall be: http://bluenet3.antcrc.utas.edu.au/mcp. 
 - The namespace identifier for gmd shall be: http://www.isotc211.org/2005/gmd
 - The namespace identifier for gco shall be: http://www.isotc211.org/2005/gco
 - The namespace identifier for gmx shall be: http://www.isotc211.org/2005/gmx
 - The namespace identifier for gml shall be: http://www.opengis.net/gml
 - The namespace identifier for xlink shall be: http://www.w3.org/1999/xlink
 - The namespace identifier for xsi shall be: http://www.w3.org/2001/XMLSchema-instance

- The root element when shown shall be mcp:MD_Metadata
- The root element should have an attribute called xsi:schemaLocation which contains a value or set of values hinting at the physical location of schemas which may be used for validation. Since this attribute provides only a hint validating parsers are allowed to ignore it and use other means of locating the relevant schemas.
- An example of the complete namespace declaration for an MCP metadata record is:

::

 <mcp:MD_Metadata 
  xmlns:mcp="http://bluenet3.antcrc.utas.edu.au/mcp"
  xmlns:gmd="http://www.isotc211.org/2005/gmd"
  xmlns:gco="http://www.isotc211.org/2005/gco"
  xmlns:gml="http://www.opengis.net/gml"
  xmlns:gmx="http://www.isotc211.org/2005/gmx"
  xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
  xmlns:xlink="http://www.w3.org/1999/xlink"
  gco:isoType="gmd:MD_Metadata"
  xsi:schemaLocation="
    http://bluenet3.antcrc.utas.edu.au/mcp 
    http://bluenet3.antcrc.utas.edu.au/mcp-1.4/schema.xsd 
    http://www.isotc211.org/2005/gmx
    http://www.isotc211.org/2005/gmx/gmx.xsd">
   (...)
 </mcp:MD_Metadata>

*Example of complete namespace declaration for an MCP metadata record*

.. index:: namespaces with prefixes are recommended and preferred

.. note:: The example of the complete namespace declaration of an MCP metadata record shown above has explicit namespace prefixes for each namespace used in the document. This is the recommended and preferred practice for MCP metadata records.

- Schemas that use the mcp namespace identifier ``http://bluenet3.antcrc.utas.edu.au/mcp`` are expected to be backwards compatible. MCP schemas with version numbers 1.3, 1.4 and 1.5-experimental all use this namespace and are backwards compatible. This means that a metadata record that validates against MCP schema version 1.3 (for example) should also validate against MCP schema version 1.4. 

MCP XML Schemas (XSDs)
----------------------

.. index:: Schema XSDs for the MCP

The schema documents (see :term:`XSD`) and codelists for the Marine Community Profile are available online at http://bluenet3.antcrc.utas.edu.au/mcp-1.4.

As the MCP is under development and contributing organisations develop and change metadata elements, code lists and content rules, an experimental version of the MCP exists at http://bluenet3.antcrc.utas.edu.au/mcp-1.5-experimental.

MCP Implementations
-------------------

Version 1.4 of the MCP (described by this document) and the experimental 1.5 version of the MCP have been implemented as plugin metadata schemas for version 2.8 of GeoNetwork opensource (see :term:`GeoNetwork`). 

.. index:: Implementations of the MCP, GeoNetwork 2.8.x (ANZMEST)

You can obtain a complete release of GeoNetwork version 2.8 with the MCP configured and ready to use in the ANZMEST package of GeoNetwork 2.8 for AU/NZ users at http://anzlicmet.bluenet.utas.edu.au.



