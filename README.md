# react-antd-object-table

This is a component to display an object using [antd Description](https://ant.design/components/descriptions/) component. The values get a copy icon to be able to copy the value to clipboard. Multiple values can be provided for a single lable with an optional separator.

## Installation

```
npm install react-antd-object-table
```

## Usage and Examples

```
import React from 'react'
import ObjectTable from 'react-antd-object-table'
import 'antd/dist/antd.css'

var dataObject = {
    'firstName': 'First',
    'lastName': 'Name',
    'city': 'Some City',
    'state': 'Some State',
    'height': 'few ft',
    'weight': 'some kgs',
}

export default class App extends React.Component {
    render() {
        return <ObjectTable data={[
            { label: 'First Name', value: dataObject.firstName },
            { label: 'Last Name', value: dataObject.lastName },
            { label: 'City / State', value: [dataObject.city, dataObject.state] },
            { label: 'Height / Weight', value: [dataObject.height, dataObject.weight], separator: '-' },
        ]} />
    }
}
```

## Disable copy icon for the whole object

Disable copy icon for the whole table, but display only for a specific value
```
<ObjectTable copyable={false} data={[
    {label: 'First Name', value: dataObject.firstName},
    {label: 'Last Name', value: dataObject.lastName, copyable: true},
    {label: 'City / State', value: [dataObject.city, dataObject.state]},
]}>
```

## Disable copy icon for a specific value

Disable copy icon for the whole table, but display only for a specific value
```
<ObjectTable data={[
    {label: 'First Name', value: dataObject.firstName},
    {label: 'Last Name', value: dataObject.lastName, copyable: false},
    {label: 'City / State', value: [dataObject.city, dataObject.state]},
]}>
```

The label and value can be ReactNodes. When ReactNodes are used as value the copy icon and copyable props are not applicable.

## Properties

| Name | Description |
| - | - |
| data | List of objects with label, value, copyable and separator as the keys |
| copyable | true/false, Enable or disable copy icon for values, defaults to true |

### Data list

data is a list of objects with the following keys:

| Key | Desciption |
| - | - |
| label | Label to show, string or ReactNode |
| value | string, list of strings, ReactNode or a list of ReactNodes |
| separator | If a list is provided for value, then show the separator between the values, default '/' |
| copyable | true or false, inherits the value of the component prop and can be overridden specifically for the item |