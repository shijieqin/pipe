---
name: "comp"
questions:
  name: "Please enter a component name."
root: "src/components"
output: "**/*"
ignore: []
---

# `{{ inputs.name }}/index.tsx`

```tsx
import React, { FC } from "react";
import { makeStyles } from "@material-ui/core";

const useStyles = makeStyles(() => ({}));

interface {{ inputs.name | pascal }}Props {
}

export const {{ inputs.name | pascal }}: FC<{{ inputs.name | pascal }}Props> = ({ }) => {
  const classes = useStyles();
  return (
    <div>
      {{ inputs.name }}
    </div>
  )
};
```

# `{{ inputs.name }}/index.stories.tsx`

```tsx
import React from "react";
import { {{ inputs.name | pascal }}, {{ inputs.name | pascal }}Props } from "./{{ inputs.name }}";

export default {
  title: "{{ inputs.name | pascal }}",
  component: {{ inputs.name | pascal }}
};

const Template: Story<{{ inputs.name | pascal }}Props> = (args) => <{{ inputs.name | pascal }} {...args} />;

export const Overview = Template.bind({});
Overview.args = {};
```
