---
layout: default
title: enuIsSelectFontStrikethough
parent: Application API
last_modified_date: now
---
# bool enuIsSelectFontStrikethough\(HVIEW pENUView\)

bool enuIsSelectFontStrikethough\(HVIEW pENUView\)

#### Parameters

* HVIEW pENUView

뷰의 핸들을 입력합니다.

#### Return Value

Type : bool

선택 텍스트 객체의 Strikethough설정여부를 반환합니다.

#### Remarks

선택된 객체가 텍스트가 아닌경우에는 false를 반환합니다.

#### Examples

```cpp
void CenuSpaceView::OnUpdateFontStrikethough(CCmdUI* pCmdUI)
{
	bool bEnable = enuIsSelectFontStrikethough(m_pENUView);
	pCmdUI->SetCheck(bEnable);
}
```



