---
layout: api
---

# sanddance-explorer

## Functions

### getEmbedHTML

```typescript
function getEmbedHTML(data: object[], displayName: string, snapshots?: Snapshot[]): string;
```

**Parameters**

| Name        | Type                                 |
| ----------- | ------------------------------------ |
| data        | object[]                             |
| displayName | string                               |
| snapshots   | [Snapshot][InterfaceDeclaration-0][] |

**Return type**

string

----------

### use

Specify the dependency libraries to use for rendering.

```typescript
function use(fabric: FabricComponents, vega: VegaBase, deck: DeckBase, layers: DeckLayerBase, luma: LumaBase): void;
```

**Parameters**

| Name   | Type             | Description                     |
| ------ | ---------------- | ------------------------------- |
| fabric | FabricComponents | Office UI Fabric React library. |
| vega   | VegaBase         |                                 |
| deck   | DeckBase         |                                 |
| layers | DeckLayerBase    |                                 |
| luma   | LumaBase         |                                 |

**Return type**

void

----------

### getColorSettingsFromThemePalette

```typescript
function getColorSettingsFromThemePalette(themePalette: Partial<IPalette>): Partial<ColorSettings>;
```

**Parameters**

| Name         | Type              |
| ------------ | ----------------- |
| themePalette | Partial<IPalette> |

**Return type**

Partial<[ColorSettings][InterfaceDeclaration-1]>

## Interfaces

### ColorSettings

```typescript
interface ColorSettings extends ColorSettings {
    clickableText?: Color;
    clickableTextHighlight?: Color;
}
```

**Extends**

ColorSettings

**Properties**

| Name                   | Type  | Optional |
| ---------------------- | ----- | -------- |
| clickableText          | Color | true     |
| clickableTextHighlight | Color | true     |

----------

### DataContent

```typescript
interface DataContent {
    data: object[];
    columns: Column[];
    snapshots?: Snapshot[];
}
```

**Properties**

| Name      | Type                                 | Optional |
| --------- | ------------------------------------ | -------- |
| data      | object[]                             | false    |
| columns   | Column[]                             | false    |
| snapshots | [Snapshot][InterfaceDeclaration-0][] | true     |

----------

### DataFile

```typescript
interface DataFile {
    displayName?: string;
    dataUrl?: string;
    snapshotsUrl?: string;
    rawText?: string;
    snapshots?: Snapshot[];
    type: DataFileType;
}
```

**Properties**

| Name         | Type                                   | Optional |
| ------------ | -------------------------------------- | -------- |
| displayName  | string                                 | true     |
| dataUrl      | string                                 | true     |
| snapshotsUrl | string                                 | true     |
| rawText      | string                                 | true     |
| snapshots    | [Snapshot][InterfaceDeclaration-0][]   | true     |
| type         | [DataFileType][TypeAliasDeclaration-1] | false    |

----------

### Snapshot

```typescript
interface Snapshot {
    title?: string;
    description?: string;
    insight?: Insight;
    image?: string;
    bgColor?: string;
}
```

**Properties**

| Name        | Type    | Optional |
| ----------- | ------- | -------- |
| title       | string  | true     |
| description | string  | true     |
| insight     | Insight | true     |
| image       | string  | true     |
| bgColor     | string  | true     |

----------

### ViewerOptions

```typescript
interface ViewerOptions extends ViewerOptions {
    colors: ColorSettings;
}
```

**Extends**

ViewerOptions

**Properties**

| Name   | Type                                    | Optional | Description                                          |
| ------ | --------------------------------------- | -------- | ---------------------------------------------------- |
| colors | [ColorSettings][InterfaceDeclaration-1] | false    | Custom colors of various parts of the visualization. |

----------

### Prefs

```typescript
interface Prefs {
    [chart: string]: SpecTypePrefs;
}
```
#### Index

```typescript
[chart: string]: SpecTypePrefs;
```

* *Parameter* `chart` - string
* *Type* SpecTypePrefs


----------

### Options

```typescript
interface Options {
    chartPrefs?: Prefs;
    tooltipExclusions?: string[];
}
```

**Properties**

| Name              | Type                            | Optional |
| ----------------- | ------------------------------- | -------- |
| chartPrefs        | [Prefs][InterfaceDeclaration-5] | true     |
| tooltipExclusions | string[]                        | true     |

----------

### Props

```typescript
interface Props {
    hideSidebarControls?: boolean;
    logoClickUrl?: string;
    logoClickTarget?: string;
    bingSearchDisabled?: boolean;
    searchORDisabled?: boolean;
    theme?: string;
    viewerOptions?: Partial<ViewerOptions>;
    initialView?: View;
    mounted?: (explorer: Explorer) => any;
    datasetElement?: Element;
    dataExportHandler?: DataExportHandler;
    topBarButtonProps?: ICommandBarItemProps[];
    snapshotProps?: SnapshotProps;
    onSnapshotClick?: (snapshot: Snapshot, selectedSnaphotIndex: number) => void;
    onView?: () => void;
    onError?: (e: any) => void;
    onSignalChanged?: () => void;
    onTooltipExclusionsChanged?: (tooltipExclusions: string[]) => void;
    systemInfoChildren?: ReactNode;
}
```

**Properties**

| Name                       | Type                                                       | Optional |
| -------------------------- | ---------------------------------------------------------- | -------- |
| hideSidebarControls        | boolean                                                    | true     |
| logoClickUrl               | string                                                     | true     |
| logoClickTarget            | string                                                     | true     |
| bingSearchDisabled         | boolean                                                    | true     |
| searchORDisabled           | boolean                                                    | true     |
| theme                      | string                                                     | true     |
| viewerOptions              | Partial<ViewerOptions>                                     | true     |
| initialView                | View                                                       | true     |
| mounted                    | (explorer: Explorer) => any                                | true     |
| datasetElement             | Element                                                    | true     |
| dataExportHandler          | DataExportHandler               | true     |
| topBarButtonProps          | ICommandBarItemProps[]                                     | true     |
| snapshotProps              | SnapshotProps                   | true     |
| onSnapshotClick            | (snapshot: Snapshot, selectedSnaphotIndex: number) => void | true     |
| onView                     | () => void                                                 | true     |
| onError                    | (e: any) => void                                           | true     |
| onSignalChanged            | () => void                                                 | true     |
| onTooltipExclusionsChanged | (tooltipExclusions: string[]) => void                      | true     |
| systemInfoChildren         | ReactNode                                                  | true     |

----------

### State

```typescript
interface State extends Insight {
    calculating: () => void;
    errors: string[];
    autoCompleteDistinctValues: AutoCompleteDistinctValues;
    search: InputSearchExpressionGroup[];
    filteredData: object[];
    sidebarClosed: boolean;
    sidebarPinned: boolean;
    dataFile: DataFile;
    dataContent: DataContent;
    specCapabilities: SpecCapabilities;
    sideTabId: SideTabId;
    dataScopeId: DataScopeId;
    selectedItemIndex: { [key: number]: number; };
    snapshots: Snapshot[];
    selectedSnapshotIndex: number;
    tooltipExclusions: string[];
    positionedColumnMapProps: PositionedColumnMapProps;
    note: string;
}
```

**Extends**

Insight

**Properties**

| Name                       | Type                                                    | Optional |
| -------------------------- | ------------------------------------------------------- | -------- |
| calculating                | () => void                                              | false    |
| errors                     | string[]                                                | false    |
| autoCompleteDistinctValues | AutoCompleteDistinctValues   | false    |
| search                     | InputSearchExpressionGroup[] | false    |
| filteredData               | object[]                                                | false    |
| sidebarClosed              | boolean                                                 | false    |
| sidebarPinned              | boolean                                                 | false    |
| dataFile                   | [DataFile][InterfaceDeclaration-3]                      | false    |
| dataContent                | [DataContent][InterfaceDeclaration-2]                   | false    |
| specCapabilities           | SpecCapabilities                                        | false    |
| sideTabId                  | SideTabId                          | false    |
| dataScopeId                | DataScopeId                        | false    |
| selectedItemIndex          | { [key: number]: number; }                              | false    |
| snapshots                  | [Snapshot][InterfaceDeclaration-0][]                    | false    |
| selectedSnapshotIndex      | number                                                  | false    |
| tooltipExclusions          | string[]                                                | false    |
| positionedColumnMapProps   | PositionedColumnMapProps     | false    |
| note                       | string                                                  | false    |

## Types

### DataExportType

```typescript
type DataExportType = DataFileType | "html";
```

**Type**

[DataFileType][TypeAliasDeclaration-1] | "html"

----------

### DataFileType

```typescript
type DataFileType = "json" | "csv" | "tsv" | "topojson";
```

**Type**

"json" | "csv" | "tsv" | "topojson"

## Classes

### [Explorer][ClassDeclaration-0]


## Variables

### capabilities

```typescript
const capabilities: { webgl: boolean; webgl2: boolean; };
```

**Type**

{ webgl: boolean; webgl2: boolean; }

----------

### themePalettes

```typescript
const themePalettes: { [theme: string]: Partial<IPalette>; };
```

**Type**

{ [theme: string]: Partial<IPalette>; }

----------

### version

```typescript
const version: string;
```

**Type**

string

[SourceFile-0]: index.html#indextsx
[FunctionDeclaration-0]: index.html#getembedhtml
[InterfaceDeclaration-0]: index.html#snapshot
[FunctionDeclaration-1]: index.html#use
[FunctionDeclaration-2]: index.html#getcolorsettingsfromthemepalette
[InterfaceDeclaration-1]: index.html#colorsettings
[InterfaceDeclaration-1]: index.html#colorsettings
[InterfaceDeclaration-2]: index.html#datacontent
[InterfaceDeclaration-0]: index.html#snapshot
[InterfaceDeclaration-3]: index.html#datafile
[InterfaceDeclaration-0]: index.html#snapshot
[TypeAliasDeclaration-1]: index.html#datafiletype
[InterfaceDeclaration-0]: index.html#snapshot
[InterfaceDeclaration-4]: index.html#vieweroptions
[InterfaceDeclaration-1]: index.html#colorsettings
[InterfaceDeclaration-5]: index.html#prefs
[InterfaceDeclaration-8]: index.html#options
[InterfaceDeclaration-5]: index.html#prefs
[InterfaceDeclaration-9]: index.html#props
[InterfaceDeclaration-10]: index.html#state
[InterfaceDeclaration-3]: index.html#datafile
[InterfaceDeclaration-2]: index.html#datacontent
[InterfaceDeclaration-0]: index.html#snapshot
[TypeAliasDeclaration-0]: index.html#dataexporttype
[TypeAliasDeclaration-1]: index.html#datafiletype
[TypeAliasDeclaration-1]: index.html#datafiletype
[ClassDeclaration-0]: explorer.html#explorer
[VariableDeclaration-0]: index.html#capabilities
[VariableDeclaration-1]: index.html#themepalettes
[VariableDeclaration-2]: index.html#version