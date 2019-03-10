# Realm CSV Exporter
RealmSwift CSV Exporter
- Slightly modifed from [Realm Cocoa Converter for macOS](https://github.com/realm/realm-cocoa-converter).
- Exports a Realm file to CSV.

## Installation
Add the following to your Podfile
```
pod 'RealmSwift'
pod 'PathKit'
```
Add `CSVDataExporter.swift` and `DataExporter.swift` to your Xcode project.

## Exporting a Realm file to CSV - Example
Exports file to device's documents directory.
```swift
// Absolute path to documents directory and, in this case, the output directory
let path = NSSearchPathForDirectoriesInDomains(.documentDirectory, .userDomainMask, true).first!
// Absolute path to Realm file
let pathString = path + "/default.realm"
            
let csvDataExporter = try! CSVDataExporter(realmFilePath: pathString)
try! csvDataExporter.export(toFolderAtPath: path)
```
