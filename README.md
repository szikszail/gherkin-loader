# gherkin-io

![Downloads](https://img.shields.io/npm/dw/gherkin-io?style=flat-square)
![Version@npm](https://img.shields.io/npm/v/gherkin-io?label=version%40npm&style=flat-square)
![Version@git](https://img.shields.io/github/package-json/v/gherking/gherkin-io/master?label=version%40git&style=flat-square)
![CI](https://img.shields.io/github/workflow/status/gherking/gherkin-io/CI/master?label=ci&style=flat-square)
![Docs](https://img.shields.io/github/workflow/status/gherking/gherkin-io/Docs/master?label=docs&style=flat-square)

Tool to read/write GHerkin feature files and work with Gherking AST

## Usage

### Read feature files

The `read` function can be used to parse feature file(s) to [AST](https://github.com/gherking/gherkin-io).

```typescript
read(pattern: string): Promise<Document[]>
```

In TypeScript:
```typescript
import {read, Document} from "gherkin-io";

const documents: Document[] = await read("./features/*.feature");
```

In JavaScript:
```javascript
const {read} = require("gherkin-io");
const documents = await read("./features/*.feature");
```

### Write feature files

The `write` function can be used to write an AST to a feature file.

```typescript
write(filePath: string, document: Document, options?: FormatterOptions): Promise<void>
```

In TypeScript:
```typescript
import {Document, write, FormatterOptions} from "gherkin-io";
const document: Document = new Document(/*...*/);
const options: FormatterOptions = {/*...*/};
await write("./test.feature", document, options);
```

In JavaScript:
```javascript
const {write, Document} = require("gherkin-io");
const document = new Document(/*...*/);
const options = {/*...*/};
await write("./test.feature", document, options);
```

`FormatterOptions` is re-exported from [gherkin-formatter](https://github.com/gherking/gherkin-formatter).

For detailed documentation see the [TypeDocs documentation](https://gherking.github.io/gherkin-io/).
