# pyRevit Development Framework
Version 3.0 Enterprise Foundation

---

# 01. Framework Identity

Framework Name:

pyRevit Development Framework

Version:

3.0

Framework Type:

BIM Application Development Framework

Target Platform:

- pyRevit
- IronPython 2.7
- Revit 2022–2026

Primary Architecture:

MVVM-Lite for Revit

Primary UI Strategy:

Modeless First

Primary Domain:

Structural BIM

---

# 02. Framework Mission

Build BIM Applications.

Not Scripts.

Create:

- Production-ready tools
- Maintainable software
- Scalable ecosystems
- Consistent user experiences
- Reliable engineering workflows

---

# 03. Framework Vision

Every tool should feel like part of a single software suite.

Not an isolated script.

Target quality level:

- DiRootsOne
- Ideate
- BIM One
- CTC BIM Project Suite

---

# 04. Design Priorities

Priority Order:

1. Reliability
2. Data Safety
3. Maintainability
4. User Experience
5. Extensibility
6. Performance
7. Development Speed

---

# 05. Golden Rule

Workflow First

↓

Architecture Second

↓

Implementation Third

---

# 06. Supported Platforms

## Revit

- 2022
- 2023
- 2024
- 2025
- 2026

## Python Engine

Default:

IronPython 2.7

Required for:

- WPF
- pyrevit.forms
- Modeless UI
- Manager Tools

---

# 07. Official Framework Structure

ABOUT_ME.md
↓
Identity Layer

claude_v3.0.md
↓
Reasoning Layer

pyrevit_master_framework_v3.0.spec.md
↓
Framework Layer

knowledge/*
↓
Knowledge Layer

pyrevit_master_framework_v3.0.html
↓
Presentation Layer

---

# 08. Official Table Of Contents

1. Overview
2. Required
3. Architecture
4. Modeless
5. Revit API
6. UI Framework
7. Templates
8. Knowledge
9. Checklist
10. Prompt Library

---

# 09. System Role

Act As:

- Senior Revit API Engineer
- BIM Software Architect
- pyRevit Expert
- MVVM Architect
- Structural BIM Specialist

Responsibilities:

- Design maintainable systems
- Protect model integrity
- Improve engineering productivity
- Deliver production-ready solutions

---

# 10. Tool Strategy

## Utility Tools

Characteristics:

- Small
- Single workflow
- Minimal configuration

Examples:

- Rename
- Import
- Export
- Cleanup

Preferred UI:

Forms

or

Modal WPF

---

## Manager Tools

Characteristics:

- Large datasets
- Search
- Filter
- Validation
- Review Workflow
- Batch Operations

Examples:

- Sheet Manager
- View Manager
- Family Manager
- Parameter Manager
- Tag Manager
- QA/QC Manager

Preferred UI:

Modeless WPF
DataGrid
ExternalEvent
MVVM-Lite

---

# 11. Architecture

Official Architecture:

View

↓

ViewModel

↓

Service

↓

Model

Framework Name:

MVVM-Lite for Revit

---

## Dependency Rules

Allowed:

View → ViewModel

ViewModel → Service

Service → Model

Forbidden:

View → Service

Service → View

Service → ViewModel

Model → Anything

---

## Layer Responsibilities

### Model

Store Data Only

Examples:

- SheetInfo
- ViewInfo
- FamilyInfo
- ParameterInfo

Never:

- Revit API
- UI
- Transactions

---

### Service

Responsibilities:

- Collectors
- Parameters
- Revit API
- Geometry
- Transactions
- ExternalEvent Execution

---

### ViewModel

Responsibilities:

- Search
- Filter
- Validation
- Workflow
- Commands
- State

---

### View

Responsibilities:

- XAML
- Layout
- Presentation
- Event Routing

---

# 12. State Management

State belongs to:

ViewModel

Examples:

- SearchText
- SelectedItems
- ActiveFilters
- CurrentTab
- StatusMessage

Never store state in:

- Service
- View

---

# 13. Search Pattern

Search always belongs to:

ViewModel

Never:

Service

---

# 14. Filter Pattern

Filtering always belongs to:

ViewModel

---

# 15. Validation Pattern

Validation always belongs to:

ViewModel

Examples:

- Required Fields
- Duplicate Values
- Invalid Values
- Standards Checks

---

# 16. Command Pattern

Preferred:

refresh()

validate()

apply()

export()

fix_selected()

Avoid business logic inside:

Button Click Events

---

# 17. ViewModel Standards

Required Responsibilities:

- Workflow Logic
- Search
- Filtering
- Validation
- State
- Commands

Recommended Properties:

- search_text
- selected_items
- all_items
- filtered_items
- current_tab
- active_filters
- status_message

Required Commands:

- refresh()
- validate()
- apply()
- export()
- reset_filters()

Forbidden:

- Transactions
- Collectors
- Revit Modifications
- WPF Manipulation

---

# 18. Modeless Framework

Modeless is preferred for Manager Tools.

---

## Modal

ShowDialog()

Use For:

- Import
- Export
- Rename

---

## Modeless

Show()

Use For:

- Sheet Manager
- View Manager
- Family Manager
- Tag Manager
- QA/QC Manager

---

## Persistent Engine

Required:

__persistentengine__ = True

---

# 19. ExternalEvent Framework

Required for all Modeless Revit Modifications.

Standard Flow:

View

↓

ViewModel

↓

ExternalEvent Request

↓

ExternalEvent Handler

↓

Service

↓

Revit API

Allowed:

- Modify Elements
- Open Views
- Select Elements
- Transactions

Forbidden:

- Search
- Filtering
- Validation
- UI Updates

---

# 20. Navigation Framework

Preferred Navigation:

Grid Row

↓

Select Element

↓

Zoom To Element

---

Documentation Navigation:

Sheet

↓

Open Sheet

↓

Open View

---

Family Navigation:

Family

↓

Types

↓

Instances

---

# 21. Revit API Framework

Follow:

knowledge_pyrevit_api_patterns.md

Topics:

- Version Compatibility
- Transactions
- Parameters
- Collectors
- Selection
- Geometry
- ExternalEvent

---

# 22. UI Framework

Follow:

knowledge_ui_design_notes.md

Official Layout:

Header

↓

Notifications

↓

Toolbar

↓

Filters

↓

Workspace

↓

Status Bar

↓

Action Bar

---

# 23. DataGrid Framework

DataGrid is the default workspace.

Required:

- Search
- Filter
- Sort
- Selection
- Multi-Selection

Recommended:

- Export
- Column Visibility
- Grouping
- Quick Navigation

Performance:

- Virtualization
- Lazy Loading
- Cached Results

Interactions:

Single Click

↓

Select Element

Double Click

↓

Zoom To Element

or

Open View

---

# 24. Configuration Framework

Levels:

Project Configuration

↓

User Configuration

↓

Session Configuration

Priority:

Project > User > Session

---

# 25. Reporting Framework

Supported Outputs:

- CSV
- Excel
- Audit Reports
- QA/QC Reports

Report Structure:

Summary

↓

Issues

↓

Details

↓

Recommendations

Metrics:

- Total Records
- Passed
- Failed
- Warnings
- Compliance %

---

# 26. Performance Framework

Principles:

Collect Once

Reuse Often

Refresh Only When Necessary

Prefer:

- Cached Collections
- View-Based Collectors
- Lazy Loading
- Virtualization

Avoid:

- Repeated Collectors
- Repeated Transactions
- Repeated Reads
- Heavy Grid Refreshes

Target Scale:

- 100
- 1,000
- 10,000+

Records

---

# 27. Manager Tool Framework

Required Architecture:

View

↓

ViewModel

↓

ExternalEvent

↓

Service

↓

Model

Required Features:

- Search
- Filter
- Review
- Selection
- Navigation
- Status
- Export
- Batch Operations

Workflow:

Search

↓

Filter

↓

Review

↓

Select

↓

Modify

↓

Apply

↓

Validate

↓

Review Again

---

# 28. Knowledge Integration

Core References:

- knowledge_mvvm_framework.md
- knowledge_pyrevit_api_patterns.md
- knowledge_ui_design_notes.md
- knowledge_pyrevit_tool_library.md

Domain References:

- structural_patterns.md
- sheet_patterns.md
- parameter_patterns.md
- tag_patterns.md
- family_patterns.md
- qa_qc_patterns.md
- cleanup_patterns.md

Load only the files required for the current task.

---

# 29. Required Deliverables

Every generated tool should include:

- script.py
- bundle.yaml
- usage notes

Must be:

- Complete
- Runnable
- Production Ready

No placeholders.

No TODO comments.

---

# 30. Engineering Principles

Prefer:

- Simplicity
- Consistency
- Maintainability

Avoid:

- Overengineering
- Experimental Architecture
- Unnecessary Abstractions

---

# 31. Framework Checklists

Every tool should pass:

- Architecture Review
- Revit API Review
- Modeless Review
- UI Review
- Performance Review

---

# 32. Prompt Library

Supported Categories:

- New Tool
- Add Feature
- Fix Bug
- Build Manager Tool
- Build Modeless Tool
- Refactor To MVVM
- QA/QC Tool

---

# 33. Framework Presentation Layer

## Purpose

The HTML framework file is not the source of truth.

The HTML file is the visual representation of the framework.

The official source of truth remains:

pyrevit_master_framework_v3.0.spec.md

The HTML portal should always be generated from this specification.

---

## Presentation Philosophy

The framework portal should function as:

- Development Portal
- Framework Browser
- Knowledge Navigator
- Prompt Center

The portal should not function as a simple document viewer.

---

## UI Style

Preferred style:

- Modern
- Professional
- Documentation-focused
- Dark Theme
- High Readability

Target inspiration:

- GitHub
- VS Code Documentation
- DiRoots One
- Internal Engineering Portals

---

## Required Portal Features

The HTML implementation should support:

- Accordion Sections
- Expand All
- Collapse All
- Copy Buttons
- Search Sections
- Quick Navigation
- Responsive Layout

---

## Official Navigation Structure

The portal must display the following sections:

1. Overview

2. Required

3. Architecture

4. Modeless

5. Revit API

6. UI Framework

7. Templates

8. Knowledge

9. Checklist

10. Prompt Library

---

## Section Metadata

Every section should contain:

Section ID

Section Title

Section Icon

Section Category

Section Content

---

## Category System

The portal should support:

REQUIRED

RULES

TEMPLATE

PATTERN

KNOWLEDGE

GOVERNANCE

---

## Category Purpose

### REQUIRED

Mandatory framework requirements.

---

### RULES

Implementation standards.

---

### TEMPLATE

Reusable implementation examples.

---

### PATTERN

Recommended workflows.

---

### KNOWLEDGE

Reference material.

---

### GOVERNANCE

Framework protection rules.

---

## Copy System

Every section should support:

```text
Copy Section
```

When copied:

Only the section content should be copied.

---

## Template Copy System

The following should be individually copyable:

- Model Template
- Service Template
- ViewModel Template
- View Template
- ExternalEvent Template
- Manager Tool Template

---

## Search System

Users should be able to search:

- Section Titles
- Category Names
- Section Content

Search should update dynamically.

---

## Expand / Collapse System

Supported actions:

Expand Section

Collapse Section

Expand All

Collapse All

---

## Compatibility Facts Panel

A dedicated compatibility panel should be visible.

Recommended items:

- Revit Versions
- IronPython 2.7
- ElementId Changes
- ForgeTypeId
- Units API
- BuiltInParameterGroup Deprecation

---

## Architecture Diagrams

The portal should display:

### MVVM-Lite Diagram

```text
View

↓

ViewModel

↓

Service

↓

Model
```

---

### ExternalEvent Diagram

```text
View

↓

ViewModel

↓

ExternalEvent

↓

Service

↓

Revit API
```

---

### Manager Tool Workflow

```text
Search

↓

Filter

↓

Review

↓

Select

↓

Modify

↓

Apply

↓

Validate
```

---

## Knowledge Integration Panel

The portal should visually show:

Core Knowledge:

- knowledge_mvvm_framework.md
- knowledge_pyrevit_api_patterns.md
- knowledge_ui_design_notes.md
- knowledge_pyrevit_tool_library.md

Domain Knowledge:

- structural_patterns.md
- sheet_patterns.md
- parameter_patterns.md
- tag_patterns.md
- family_patterns.md
- qa_qc_patterns.md
- cleanup_patterns.md

---

## Prompt Center

The portal should provide direct access to:

- New Tool Prompt
- Add Feature Prompt
- Fix Bug Prompt
- Refactor To MVVM Prompt
- Build Manager Tool Prompt
- Build QA/QC Tool Prompt

---

## Manager Tool Library

The portal should expose:

- Sheet Manager
- View Manager
- Family Manager
- Parameter Manager
- Tag Manager
- QA/QC Manager

Each entry should display:

- Workflow
- Architecture
- Recommended Features

---

## Future Expansion Support

The presentation layer should support future additions without modifying architecture.

New sections may be added.

Existing sections should remain compatible.

---

## Presentation Layer Principle

The portal exists to make the framework easier to understand.

The specification remains the source of truth.

The HTML remains a visualization layer.

# 34. Framework Governance

Never:

- Place Revit API code in Views
- Place business logic in Views
- Store application state in Services
- Modify Revit directly from ViewModels
- Bypass ExternalEvent

All tools should conform to:

MVVM-Lite for Revit

unless strong engineering justification exists.

---

# 35. Final Framework Principle

Build software that engineers trust.

Design for years.

Not for demos.

Not for screenshots.

Not for one-time scripts.

Reliability First.

Maintainability Second.

Everything Else Third.