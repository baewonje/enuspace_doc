---
layout: default
title: Create3DInline
parent: Script API
last_modified_date: now
---
# Create3DInline\(id, strUrl, transx, transy, transz\)

Create3DInline\(\)

#### Parameters

id : id값을 입력합니다.

strUrl : x3d파일의 이름을 입력합니다.

transx : x축의 이동값을 입력합니다.

transy : y축의 이동값을 입력합니다.

transz : z축의 이동값을 입력합니다.

#### Return Value

none

#### Remarks

스크립트를 이용하여 동적으로 Inline 객체를 생성합니다. 생성된 객체의 속성을 변경하고자 하는 경우에는 [SetAttribute3D\(\)](https://expnuni.github.io/enuspace_doc/docs/enusscriptapi_setattribute3d/)함수를 이용합니다.

```lua
-- lua
Create3DInline("ID_INLINE", "picture\\airplane.x3d", 0, 0, 0)
```

```js
// javascript
Create3DInline("ID_INLINE", "picture\\airplane.x3d", 0, 0, 0);
```

#### 

#### Examples

```lua
-- lua
function _onmousedown()
    Create3DInline("ID_INLINE", "picture\\airplane.x3d", 0, 0, 0)
end
```

```js
// JavaScript
function _onmousedown()
{    
    Create3DInline("ID_INLINE", "picture\\airplane.x3d", 0, 0, 0);
}
```



