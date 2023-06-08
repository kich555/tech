---
transition: slide-up
---
# Form

<div style='margin-top:24px'>Schema</div>
<br/>

```tsx {all|3|8-12|16-35|40-48|45} {maxHeight:'380px'}
const CampaignFormSchema = z
  .object({
    name: z.string().min(2, {message: REQUIRED_ERROR_MESSAGE}).max(80, {message: CAMPAIGN_NAME_ERROR_MESSAGE}),
    budget: z.number().or(z.string().min(1, {message: REQUIRED_ERROR_MESSAGE})),
    startedAt: z.string().min(1, {message: REQUIRED_ERROR_MESSAGE}).or(z.date()),
    endedAt: z.string().min(1, {message: REQUIRED_ERROR_MESSAGE}).or(z.date()),
    createdAt: z.string().optional(),
    landingUrl: z
      .string()
      .min(1, {message: REQUIRED_ERROR_MESSAGE})
      .max(500, {message: CAMPAIGN_LANDING_URL_MESSAGE})
      .regex(LANDING_URL_REGEX, {message: CAMPAIGN_LANDING_URL_MESSAGE}),
    landingType: z.string().min(1, {message: CAMPAIGN_LANDING_TYPE_MESSAGE}),
    inventories: z.array(z.string()).min(1, {message: REQUIRED_ERROR_MESSAGE}),
    imageUrl: z.string().optional(),
    imgFile:
      typeof window === 'undefined'
        ? z.any()
        : z
            .instanceof(File, {message: CAMPAIGN_FILE_MESSAGE})
            .optional()
            .superRefine((arg, ctx) => {
              if (typeof arg === 'undefined') return;
              const fileSizeKB = Math.round(arg.size / 1024);
              const fileExtension = arg.name.substring(arg.name.lastIndexOf('.') + 1);
              if (fileSizeKB >= 200 || fileExtension !== ('png' || 'jpg')) {
                ctx.addIssue({
                  code: z.ZodIssueCode.too_big,
                  maximum: 3,
                  type: 'array',
                  inclusive: true,
                  message: CAMPAIGN_FILE_CONDITION_MESSAGE,
                });
              }
            }),
    memo: z.string(),
    companyName: z.string().optional(),
    isActive: z.boolean().optional(),
  })
  .superRefine((arg, ctx) => {
    if (typeof arg.imageUrl !== 'string' && typeof arg.imgFile === 'undefined') {
      ctx.addIssue({
        code: z.ZodIssueCode.custom,
        message: CAMPAIGN_FILE_MESSAGE,
        path: ['imgFile'],
      });
    }
  });
```

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