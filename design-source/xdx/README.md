# Xpedition Design Source Files

This directory contains the original Mentor Graphics Xpedition (XDX) PCB design source files from 2014.


## File Contents

```
design-source/xdx/
├── README.md           # This file
├── schematic.eds       # Schematic in EDIF format (600 KB)
├── pcb/                # PCB layout source files
└── library/            # Component libraries
    ├── SymbolLibs/     # Schematic symbol libraries
    │   ├── custom/     # Custom symbols (formerly "JohnEnglish")
    │   ├── Borders/    # Title blocks and sheet borders
    │   ├── builtin/    # Built-in Xpedition symbols
    │   └── Globals/    # Global symbols (power, ground, etc.)
    ├── PartsDBLibs/    # Parts database
    │   └── custom.pdb  # Custom parts database
    └── Library.*       # Library configuration and database files
```

## Opening the Design

### Requirements

To open and edit these design files, you need Mentor Graphics Xpedition

## Software Version

**Design Tool:** Mentor Graphics Xpedition XDX (formerly DxDesigner)
**Version:** EEVX.1 <643606> (August 2014)
**Format:** EDIF (Electronic Design Interchange Format) for schematic

### Version Compatibility

**⚠️ Warning:** These files were created in 2014 with an older version of Xpedition.

**Compatibility Considerations:**
- **Newer Versions:** Modern Xpedition should be able to import EDIF files, but some formatting may be lost
- **Older Versions:** May not have all features used in the design
- **Symbol Libraries:** The custom symbol library has been renamed from "JohnEnglish" to "custom" for this release


### Library Notes

The design references these libraries:
- **custom** - Custom component symbols specific to this project
- **Borders** - Sheet borders and title blocks
- **builtin** - Standard Xpedition symbols
- **Globals** - Power and ground symbols


## For Viewing Only

If you only want to view the schematic without opening Xpedition:

**Recommended:** Use the PDF schematic in `hardware/schematic.pdf`

The PDF provides a complete, readable view of the 5-sheet schematic and does not require XDX


## Known Limitations

1. **Legacy Format:** 2014-era Xpedition may not be fully compatible with modern versions
2. **Library Dependencies:** Custom library must be properly installed
3. **PCB Constraints:** Some design rules may not migrate perfectly
4. **No 3D Models:** Component 3D models were not exported with the design

## References

- [Mentor Graphics Xpedition](https://eda.sw.siemens.com/) - Official product page
- [EDIF Standard](https://en.wikipedia.org/wiki/EDIF) - Wikipedia overview
- This project's schematic: `../../hardware/schematic.pdf`

## Support

**Note:** These are archived design files from a 2014 student project.

- No warranty or support is provided for the Xpedition source files
- For design questions, refer to the PDF schematic and documentation
- For tool-specific questions, consult Mentor Graphics support or forums

---

*If you successfully open and work with these files in a modern Xpedition installation, please consider documenting the process and contributing back to this repository!*
