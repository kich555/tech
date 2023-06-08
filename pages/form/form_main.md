---
transition: slide-up
---
# Form

<div style='margin-top:24px'>React-hook-form</div>
<br/>
<div grid="~ cols-2 gap-2" m="-t-2">

```tsx {all|3} {height:'400px'}
const methods = useForm<CampaignFormSchemaType>({
    defaultValues: campaign,
    resolver: zodResolver(CampaignFormSchema),
  });
```

```tsx {all|1,9} {maxHeight:'300px'}
<FormProvider {...methods}>
  <Box
    component="form"
    encType="multipart/form-data"
    onSubmit={methods.handleSubmit}
  >
    ...///
  </Box>
</FormProvider>
```
</div>

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(52deg, #34dae7 3%, #0daeff 97%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
#dkcbmlkdmfg {
  display: none;
}
</style>

<!-- renderReactElement 함수는 Nextjs 내부 소스코드 중에서 최종적으로 요소 랜더링을 담당하는 함수입니다. 
보시는 것처럼 shouldHydrate 값을 통해 요소를 hydrate할지, render할지 결정합니다. 

  -->