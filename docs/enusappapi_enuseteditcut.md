---
layout: default
title: enuSetEditCut
parent: Application API
last_modified_date: now
---
# void enuSetEditCut\(HVIEW pENUView\)

void enuSetEditCut\(HVIEW pENUView\)

#### Parameters

* HVIEW pENUView

뷰의 핸들을 입력합니다.

#### Return Value

Type : NONE

#### Remarks

Cut 명령을 수행합니다. 선택 객체에 대하여 잘라내기 루틴을 수행합니다. enuSetEditPaste\(\)함수를 통하여 붙여넣기를 수행합니다.

#### Examples

```cpp
void CenuSpaceView::OnEditCut()
{
	enuSetEditCut(m_pENUView);
}
```



