# Vantus File Indexer | Windows desktop search prototype

**Problem:** Finding and organizing files across a Windows workstation can require more than basic folder-name searches, particularly when content extraction and repeatable indexing matter.

This repository contains a C#/.NET solution with a WinUI 3 desktop shell, a separate indexing engine, shared core libraries, Windows packaging, and test projects.

## Architecture entry points

- [Vantus.App](Vantus.App/) is the WinUI 3 application, targeting .NET 8 on Windows.
- [Vantus.Engine](Vantus.Engine/) contains the indexing-engine project and dependencies for SQLite, document parsing, and text extraction.
- [Vantus.Core](Vantus.Core/) contains shared data and application contracts.
- [Vantus.Tests](Vantus.Tests/) contains xUnit-oriented verification source.
- [Vantus.Packaging](Vantus.Packaging/) contains the Windows application packaging project.

## Build and evaluation

[Windows build and installation guide](BUILD_AND_INSTALL.md) describes the Visual Studio 2022 prerequisites, Windows App SDK tooling and MSIX packaging route.

Use an isolated Windows test environment. Open `Vantus.FileIndexer.sln` and build the required target platform after restoring dependencies. A test-project reference or packaging project does not by itself prove a passing solution build, installed binary, indexing accuracy, or field performance.

## Status and evidence boundary

**Research/development prototype; Windows deployment and performance are not independently certified.**

Source shows the intended separation of desktop UI, indexed persistence, document-processing dependencies, and test scaffolding. Actual throughput, cancellation behavior, extraction quality, privacy boundaries, and Windows installation should be measured before offering the product to end users.

No license is granted by this README. Preserve third-party dependency notices and review rights before redistributing compiled binaries.
