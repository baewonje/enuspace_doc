---
layout: default
title: enuSetSelectLineDashes
parent: Application API
last_modified_date: now
---
# void enuSetSelectLineDashes\(HVIEW pENUView, wchar\_t\* strDashes\)

void enuSetSelectLineDashes\(HVIEW pENUView, wchar\_t\* strDashes\)

#### Parameters

* HVIEW pENUView

뷰의 핸들을 입력합니다.

* wchar\_t\* strDashes

객체의 라인 Dash값을 입력합니다. \(ex. "1 2 1"\)

#### Return Value

Type : NONE

#### Remarks

선택 객체의 라인 Dash 설정을 수행합니다. SVG에서는 stroke-dasharray속성입니다.

```xml
<?xml version="1.0" encoding="UTF-16"?>
<svg
    id="ID_1enfXB"
    stroke="rgb(0,119,189)"
    stroke-opacity="1.00"
    stroke-width="1.00"
    transform="translate(0.00,0.00) rotate(0.00) scale(1.0000, 1.0000)"
    pg-xcenter="0.00"
    pg-ycenter="0.00"
    style="stroke:rgb(127,127,127);stroke-opacity:1.00;stroke-width:2.00;stroke-dasharray:1,1,1;"
    enuspace-version="3.0.2.0"
    xmlns="http://www.w3.org/2000/svg"
    xmlns:xlink="http://www.w3.org/1999/xlink"
    pg-create-time="2018-2-19 7:6:45.663"
    width="1920"
    height="1080"
>
    <polyline
        id="ID_1enn320"
        stroke="rgb(0,119,189)"
        stroke-opacity="1.00"
        stroke-width="2.00"
        transform="translate(170.00,185.00) rotate(0.00) scale(1.0000, 1.0000)"
        pg-xcenter="0.00"
        pg-ycenter="0.00"
        stroke-linecap="butt"
         stroke-linejoin="miter"
         stroke-dasharray="1 2 1"
         points="0,0 96.000000,-47.000000 133.000000,-5.000000 193.000000,-23.000000 260.000000,16.000000"
        pg-begin-arrow-type="none"
        pg-begin-arrow-size="5.00"
        pg-begin-arrow-angle="60.00"
        pg-begin-arrow-span="medium2"
        pg-end-arrow-type="none"
        pg-end-arrow-size="5.00"
        pg-end-arrow-angle="60.00"
        pg-end-arrow-span="medium2"
    >
    </polyline>
</svg>
```

#### Examples

```cpp
void CenuSpaceView::OnObjectLineDashes(UINT nID)
{
    int weight = -1;
    if (nID == ID_OBJECT_LINEDASHES)
    {
        weight = ((CMainFrame*)AfxGetMainWnd())->GetWeightFromLineWeight(ID_OBJECT_LINEDASHES);

        CString strDash = GetStrokeDashValue(weight);

        enuSetSelectLineDashes(m_pENUView, strDash.GetBuffer(0));
    }
}
```



