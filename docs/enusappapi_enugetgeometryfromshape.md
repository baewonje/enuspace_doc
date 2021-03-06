---
layout: default
title: enuGetGeometryFromShape
parent: Application API
last_modified_date: now
---
# HNODE enuGetGeometryFromShape\(HX3D pX3DHandler, HNODE node\)

HNODE enuGetGeometryFromShape\(HX3D pX3DHandler, HNODE node\)

#### Parameters

* HX3D pX3DHandler

X3D 픽쳐 핸들러를 지정합니다.

* HNODE node

3D 객체의 Shape NODE 핸들을 지정합니다.

#### Return Value

Type : HNODE

Geometry노드를 반환합니다.

#### Remarks

```xml
<?xml version="1.0" encoding="UTF-16" ?>
<x3d
>
    <Scene
    >
        <Transform
            rotation="0.000000,0.000000,0.000000"
            scaleOrientation="0.000000,0.000000,1.000000,0.000000"
        >
            <Shape
                id="ID_1elRo8"
            >
                <Appearance
                >
                    <Material
                        ambientIntensity="0.200000"
                        shininess="0.200000"
                        transparency="1.000000"
                        diffuseColor="0.800000,0.800000,0.800000"
                        emissiveColor="0.000000,0.000000,0.000000"
                        specularColor="0.000000,0.000000,0.000000"
                    >
                    </Material>
                </Appearance>
                <Box
                    size="10.000000,10.000000,10.000000"
                >
                </Box>
            </Shape>
        </Transform>
    </Scene>
</x3d>
```

#### Examples

```cpp
HVIEW ViewHandle = NULL; 
void CSampleView::OnInitialUpdate() 
{ 
    CView::OnInitialUpdate(); 

    enuCreateProject(); 

    // Load Project
    enuLoadProjectFile(L"Project\\sample.enup"); 

    // Create View
    ViewHandle = enuCreate3DView(this->m_hWnd); 

    // ENU View Attach Set Page 
    enuSetX3dPageView(ViewHandle , L"picture\\core_3d.x3d");

    // Get X3D picture handle
    HX3D pX3D = enuGetX3DHandler(ViewHandle); 

    // Create 3D Cylinder.
    HNODE hGeo = enuCreate3DCylinder(pX3D,"MyCylinder", 100, 100, 10, 0, 0, 0);        

    HX3D hShape = enuGetShapeFromGeometry(pX3D, hGeo);
    HX3D hApp = enuGetAppearanceFromShape(pX3D, hShape);

    HX3D hSeGeo = enuGetGeometryFromShape(pX3D, hShape);        // hSeGeo and hGeo equal.
    HX3D hMat = enuGetMaterialFromGeometry(pX3D, hGeo);  
    HX3D hSeMat = enuGetMaterialFromAppearance(pX3D, hApp);     // hSeMat and hMat equal.
    HX3D hTrans =enuGetTransformFromGeometry(pX3D, hGeo);

    enu3DSetAttributeByNode(pX3D, hMat, L"transparency", L"0.5");
}
```



