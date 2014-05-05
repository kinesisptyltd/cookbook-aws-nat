# cookbook-nat

Cookbook to set up a non CentOS NAT instance for Amazon VPCs.

## Requirements

Only tested on Ubuntu 14.04, but should work on earlier versions.

## Usage

Just include `nat` in your node's `run_list`:

```json
{
  "run_list": [
    "recipe[nat]"
  ]
}
```

## License

    Copyright 2014 Christopher Chow

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
