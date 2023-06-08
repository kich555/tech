---
transition: my-transition
---
<div style='height:100%; overflowY:scroll;'>
<br/>
<br/>
<div grid="~ cols-2 gap-2" m="-t-2">
<div>
  <div id='title'>Mantine UI</div>
  <img src="/typo.png" class="mt-4  rounded shadow"  />
</div>

```tsx{0|1-24} {maxHeight:'460px'}
import React from 'react';
import {Text, type TextProps} from '@mantine/core';

type TypographyProps = Omit<TextProps, 'size' | 'weight'> & {
  children: React.ReactNode;
  type?:
    | 'headline1'
    | 'headline2'
    | 'headline3'
    | 'headline4'
    | 'headline5'
    | 'headline6'
    | 'subtitle1'
    | 'subtitle2'
    | 'text1'
    | 'text1bold'
    | 'text2'
    | 'text2bold'
    | 'text3'
    | 'text3bold'
    | 'caption'
    | 'overline'
    | 'landingbold'
    | 'footer';
};

function Typography({children, type = 'text2', ...textProps}: TypographyProps) {
  const TypographyEnum = {
    headline1: (
      <Text {...textProps} size={42} weight={700} sx={{...textProps.sx, lineHeight: '54px'}}>
        {children}
      </Text>
    ),
    headline2: (
      <Text {...textProps} size={40} weight={700} sx={{...textProps.sx, lineHeight: '52px'}}>
        {children}
      </Text>
    ),
    headline3: (
      <Text {...textProps} size={36} weight={700} sx={{...textProps.sx, lineHeight: '46px'}}>
        {children}
      </Text>
    ),
    headline4: (
      <Text {...textProps} size={28} weight={700} sx={{...textProps.sx, lineHeight: '36px'}}>
        {children}
      </Text>
    ),
    headline5: (
      <Text {...textProps} size={24} weight={700} sx={{...textProps.sx, lineHeight: '32px'}}>
        {children}
      </Text>
    ),
    headline6: (
      <Text {...textProps} size={20} weight={700} sx={{...textProps.sx, lineHeight: '26px'}}>
        {children}
      </Text>
    ),
    subtitle1: (
      <Text {...textProps} size={16} weight={700} sx={{...textProps.sx, lineHeight: '26px'}}>
        {children}
      </Text>
    ),
    subtitle2: (
      <Text {...textProps} size={15} weight={400} sx={{...textProps.sx, lineHeight: '20px'}}>
        {children}
      </Text>
    ),
    text1: (
      <Text {...textProps} size={17} weight={400} sx={{...textProps.sx, lineHeight: '28px'}}>
        {children}
      </Text>
    ),
    text1bold: (
      <Text {...textProps} size={17} weight={700} sx={{...textProps.sx, lineHeight: '28px'}}>
        {children}
      </Text>
    ),
    text2: (
      <Text {...textProps} size={16} weight={400} sx={{...textProps.sx, lineHeight: '26px'}}>
        {children}
      </Text>
    ),
    text2bold: (
      <Text {...textProps} size={16} weight={700} sx={{...textProps.sx, lineHeight: '26px'}}>
        {children}
      </Text>
    ),
    text3: (
      <Text {...textProps} size={14} weight={400} sx={{...textProps.sx, lineHeight: '22px'}}>
        {children}
      </Text>
    ),
    text3bold: (
      <Text {...textProps} size={14} weight={700} sx={{...textProps.sx, lineHeight: '22px'}}>
        {children}
      </Text>
    ),
    caption: (
      <Text {...textProps} size={12} weight={400} sx={{...textProps.sx, lineHeight: '20px'}}>
        {children}
      </Text>
    ),
    overline: (
      <Text {...textProps} size={11} weight={400} sx={{...textProps.sx, lineHeight: '26px'}}>
        {children}
      </Text>
    ),
    landingbold: (
      <Text {...textProps} size={22} weight={700} sx={{...textProps.sx, lineHeight: '38.4px'}}>
        {children}
      </Text>
    ),
    footer: (
      <Text {...textProps} size={11} weight={400} sx={{...textProps.sx, lineHeight: '20px'}}>
        {children}
      </Text>
    ),
  };

  return TypographyEnum[type];
  // return <Text>Typography</Text>;
}

export default Typography;

```
</div>
</div>





<style>
#title { 
  font-weight: 700;
  font-size: 60px;
  line-height: none !important;
  background-color: #2B90B6;
  background-image: linear-gradient(52deg, #34dae7 3%, #0daeff 97%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
h1,h2 {
  line-height: none !important;
  background-color: #2B90B6;
  background-image: linear-gradient(52deg, #34dae7 3%, #0daeff 97%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}

.my-transition-enter-active,
.my-transition-leave-active {
  transition: opacity 0.9s ease;
}

.my-transition-enter-from,
.my-transition-leave-to {
  opacity: 0;
}
</style>
