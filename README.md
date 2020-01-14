# Serial Message Format
To make serial communication more easy and consistent, this defines a very simple message format.

## Format
**type&lt;delimiter&gt;content**

| Component | Meaning |
| --------- | ------- |
| type | Contains the type of the message |
| &lt;delimiter&gt; | Containts the delimiter, without the angle brackets. Default is `:` |
| conent | Contains the message body |

Example:
* type: `error`
* delimiter: `:`
* content: `ExampleError 123`
* Whole message: `error:ExampleError 123`
## Interpretation of messages
Type and content could be extracted with the following regular expressions, using the default delimiter `:`:
* type: ^[^:]*
* content: (?<=:).*$

The message type is always the part **before** the first occurence of the delimiter, while the content is usually the part **after** the first occurence of the delimiter until the end of the message.

# License
```
   Copyright 2019 Jan-Eric Schober

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.
```
