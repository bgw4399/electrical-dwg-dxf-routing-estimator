# Electrical DWG/DXF Routing Estimator

CAD/DXF-based electrical construction estimation and routing application.

## Overview

This project is an applied IT system being developed with Leean Construction Engineering Co., Ltd. It analyzes electrical construction drawings, estimates quantities/costs, and visualizes baseline and optimized routing over CAD/DXF views.

## Core Features

- DWG upload and DXF fallback analysis
- FastAPI server for estimate/routing APIs
- CAD/DXF viewer with route overlays
- baseline vs optimized path comparison
- standard cost database sync and recalculation
- patch bbox review and vector-based stitching direction
- KEC constraint-aware routing experiments

## Main Technical Problem

The early system mixed CAD coordinates, image pixels, and separate patch bbox coordinates. This caused route overlays and patch positions to drift.

The current direction is:

- use the DXF viewer as the unified coordinate frame
- render baseline and optimized paths as overlays on the CAD vector view
- separate DWG native viewing from DXF fallback control
- improve path optimization from simple MST/straight links toward Hanan Grid and rectilinear Steiner-style trunk/branch routing

## Stack

- Python
- FastAPI
- pandas/openpyxl
- DXF/DWG conversion tooling
- JavaScript/HTML CAD viewer
- route optimization and estimation logic

## Public Sharing Notes

Do not commit client drawings, confidential estimates, company-specific source Excel files, or APS credentials. Use synthetic/sample drawings and screenshots only.
