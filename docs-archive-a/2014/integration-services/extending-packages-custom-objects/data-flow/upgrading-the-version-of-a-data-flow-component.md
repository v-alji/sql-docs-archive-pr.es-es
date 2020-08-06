---
title: Actualizar la versión de un componente de flujo de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- PerformUpgrade method
- custom data flow components [Integration Services], upgrading version
- data flow components [Integration Services], upgrading version
- upgrading data flow components [Integration Services]
ms.assetid: c2a298c6-01b3-4ad1-884d-6108165eb56e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f494793a20f1cdcd108553278b82a44daeea75ee
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677778"
---
# <a name="upgrading-the-version-of-a-data-flow-component"></a><span data-ttu-id="8a2c5-102">Actualizar la versión de un componente de flujo de datos</span><span class="sxs-lookup"><span data-stu-id="8a2c5-102">Upgrading the Version of a Data Flow Component</span></span>
  <span data-ttu-id="8a2c5-103">Los paquetes que se crearon con una versión anterior de su componente pueden contener metadatos que ya no son válidos, como propiedades personalizadas cuyo uso se ha modificado en versiones más recientes del componente.</span><span class="sxs-lookup"><span data-stu-id="8a2c5-103">Packages that were created with an older version of your component may contain metadata that is no longer valid, such as custom properties whose usage has been modified in newer versions of the component.</span></span> <span data-ttu-id="8a2c5-104">Puede invalidar el método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PerformUpgrade%2A> de la clase base <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent> para actualizar los metadatos previamente guardados en paquetes anteriores para reflejar las propiedades actuales de su componente.</span><span class="sxs-lookup"><span data-stu-id="8a2c5-104">You can override the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PerformUpgrade%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent> base class to update the metadata previously saved in older packages to reflect the current properties of your component.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8a2c5-105">Al volver a compilar un componente personalizado para una nueva versión de [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], no tiene que cambiar el valor de la propiedad <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute.CurrentVersion%2A> si las propiedades del componente no han cambiado.</span><span class="sxs-lookup"><span data-stu-id="8a2c5-105">When you recompile a custom component for a new version of [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], you do not have to change the value of the <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute.CurrentVersion%2A> property if the component's properties have not changed.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8a2c5-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8a2c5-106">Example</span></span>  
 <span data-ttu-id="8a2c5-107">El ejemplo siguiente contiene el código de la versión 2.0 de un componente de flujo de datos ficticio.</span><span class="sxs-lookup"><span data-stu-id="8a2c5-107">The following sample contains code from version 2.0 of a fictitious data flow component.</span></span> <span data-ttu-id="8a2c5-108">El nuevo número de versión se define en la propiedad <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute.CurrentVersion%2A> de <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute>.</span><span class="sxs-lookup"><span data-stu-id="8a2c5-108">The new version number is defined in the <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute.CurrentVersion%2A> property of the <xref:Microsoft.SqlServer.Dts.Pipeline.DtsPipelineComponentAttribute>.</span></span> <span data-ttu-id="8a2c5-109">El componente tiene una propiedad que define la manera de administrar los valores numéricos que superan un umbral.</span><span class="sxs-lookup"><span data-stu-id="8a2c5-109">The component has a property that defines how numeric values that exceed a threshold are to be handled.</span></span> <span data-ttu-id="8a2c5-110">En la versión 1.0 del componente ficticio, esta propiedad se denominó `RaiseErrorOnInvalidValue` y aceptó un valor booleano de true o false.</span><span class="sxs-lookup"><span data-stu-id="8a2c5-110">In version 1.0 of the fictitious component, this property was named `RaiseErrorOnInvalidValue` and accepted a Boolean value of true or false.</span></span> <span data-ttu-id="8a2c5-111">En la versión 2.0 del componente ficticio, se ha cambiado el nombre de la propiedad a `InvalidValueHandling` y acepta uno de cuatro valores posibles de una enumeración personalizada.</span><span class="sxs-lookup"><span data-stu-id="8a2c5-111">In version 2.0 of the fictitious component, the property has been renamed to `InvalidValueHandling` and accepts one of four possible values from a custom enumeration.</span></span>  
  
 <span data-ttu-id="8a2c5-112">El método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PerformUpgrade%2A> que se invalida en el ejemplo siguiente realiza las acciones que se enumeran a continuación:</span><span class="sxs-lookup"><span data-stu-id="8a2c5-112">The overridden <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PerformUpgrade%2A> method in the following sample performs the following actions:</span></span>  
  
-   <span data-ttu-id="8a2c5-113">Obtiene la versión actual del componente.</span><span class="sxs-lookup"><span data-stu-id="8a2c5-113">Gets the current version of the component.</span></span>  
  
-   <span data-ttu-id="8a2c5-114">Obtiene el valor de la propiedad personalizada anterior.</span><span class="sxs-lookup"><span data-stu-id="8a2c5-114">Gets the value of the old custom property.</span></span>  
  
-   <span data-ttu-id="8a2c5-115">Quita una la propiedad anterior de la colección de propiedades personalizadas.</span><span class="sxs-lookup"><span data-stu-id="8a2c5-115">Removes the old property from the custom property collection.</span></span>  
  
-   <span data-ttu-id="8a2c5-116">Si es posible, establece el valor de la nueva propiedad personalizada a partir del valor de la propiedad anterior.</span><span class="sxs-lookup"><span data-stu-id="8a2c5-116">Sets the value of the new custom property based on the value of the old property, if possible.</span></span>  
  
-   <span data-ttu-id="8a2c5-117">Establece los metadatos de la versión en la versión actual del componente.</span><span class="sxs-lookup"><span data-stu-id="8a2c5-117">Sets the version metadata to the current version of the component.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8a2c5-118">El motor de flujo de datos pasa su propio número de versión al método <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PerformUpgrade%2A> en el parámetro *pipelineVersion*.</span><span class="sxs-lookup"><span data-stu-id="8a2c5-118">The data flow engine passes its own version number into the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PerformUpgrade%2A> method in the *pipelineVersion* parameter.</span></span> <span data-ttu-id="8a2c5-119">Este parámetro no es útil en la versión 1.0 de [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], pero sí puede ser útil en versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="8a2c5-119">This parameter is not useful in version 1.0 of [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], but may become useful in subsequent versions.</span></span>  
  
 <span data-ttu-id="8a2c5-120">El código de ejemplo usa únicamente los dos valores de enumeración que asignan directamente a los valores booleanos anteriores para la propiedad personalizada.</span><span class="sxs-lookup"><span data-stu-id="8a2c5-120">The sample code uses only the two enumeration values that map directly to the prior Boolean values for the custom property.</span></span> <span data-ttu-id="8a2c5-121">Los usuarios pueden seleccionar otros valores de enumeración disponibles a través de la interfaz de usuario personalizada del componente, bien en el Editor avanzado o bien mediante programación.</span><span class="sxs-lookup"><span data-stu-id="8a2c5-121">Users can select the other available enumeration values through the component's custom user interface, in the Advanced Editor, or programmatically.</span></span> <span data-ttu-id="8a2c5-122">Para obtener información acerca de cómo mostrar valores de enumeración para una propiedad personalizada en el Editor avanzado, vea "Crear propiedades personalizadas" en [Métodos en tiempo de diseño de un componente de flujo de datos](design-time-methods-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="8a2c5-122">For information on displaying enumeration values for a custom property in the Advanced Editor, see "Creating Custom Properties" in [Design-time Methods of a Data Flow Component](design-time-methods-of-a-data-flow-component.md).</span></span>  
  
```vb  
Imports Microsoft.SqlServer.Dts.Pipeline  
Imports Microsoft.SqlServer.Dts.Pipeline.Wrapper  
  
<DtsPipelineComponent(ComponentType:=ComponentType.Transform, CurrentVersion:=2)> _  
Public Class PerformUpgrade  
  Inherits PipelineComponent  
  
  ' Define the set of possible values for the new custom property.  
  Private Enum InvalidValueHandling  
    Ignore  
    FireInformation  
    FireWarning  
    FireError  
  End Enum  
  
  Public Overloads Overrides Sub PerformUpgrade(ByVal pipelineVersion As Integer)  
  
    ' Obtain the current component version from the attribute.  
    Dim componentAttribute As DtsPipelineComponentAttribute = _  
      CType(Attribute.GetCustomAttribute(Me.GetType, _  
      GetType(DtsPipelineComponentAttribute), False), _  
      DtsPipelineComponentAttribute)  
    Dim currentVersion As Integer = componentAttribute.CurrentVersion  
  
    ' If the component version saved in the package is less than  
    '  the current version, Version 2, perform the upgrade.  
    If ComponentMetaData.Version < currentVersion Then  
  
      ' Get the current value of the old custom property, RaiseErrorOnInvalidValue,   
      ' and then remove the property from the custom property collection.  
      Dim oldValue As Boolean = False  
      Try  
        Dim oldProperty As IDTSCustomProperty100 = _  
          ComponentMetaData.CustomPropertyCollection("RaiseErrorOnInvalidValue")  
        oldValue = CType(oldProperty.Value, Boolean)  
        ComponentMetaData.CustomPropertyCollection.RemoveObjectByIndex("RaiseErrorOnInvalidValue")  
      Catch ex As Exception  
        ' If the old custom property is not available, ignore the error.  
      End Try  
  
      ' Set the value of the new custom property, InvalidValueHandling,  
      '  by using the appropriate enumeration value.  
      Dim newProperty As IDTSCustomProperty100 = _  
        ComponentMetaData.CustomPropertyCollection("InvalidValueHandling")  
      If oldValue = True Then  
        newProperty.Value = InvalidValueHandling.FireError  
      Else  
        newProperty.Value = InvalidValueHandling.Ignore  
      End If  
  
    End If  
  
    ' Update the saved component version metadata to the current version.  
    ComponentMetaData.Version = currentVersion  
  
  End Sub  
  
End Class  
```  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Pipeline;  
using Microsoft.SqlServer.Dts.Pipeline.Wrapper;  
  
[DtsPipelineComponent(ComponentType = ComponentType.Transform, CurrentVersion = 2)]  
public class PerformUpgradeCS :  
  PipelineComponent  
  
  // Define the set of possible values for the new custom property.  
{  
  private enum InvalidValueHandling  
  {  
    Ignore,  
    FireInformation,  
    FireWarning,  
    FireError  
  };  
  
  public override void PerformUpgrade(int pipelineVersion)  
  {  
  
    // Obtain the current component version from the attribute.  
    DtsPipelineComponentAttribute componentAttribute =   
      (DtsPipelineComponentAttribute)Attribute.GetCustomAttribute(this.GetType(), typeof(DtsPipelineComponentAttribute), false);  
    int currentVersion = componentAttribute.CurrentVersion;  
  
    // If the component version saved in the package is less than  
    //  the current version, Version 2, perform the upgrade.  
    if (ComponentMetaData.Version < currentVersion)  
  
    // Get the current value of the old custom property, RaiseErrorOnInvalidValue,   
    // and then remove the property from the custom property collection.  
    {  
      bool oldValue = false;  
      try  
      {  
        IDTSCustomProperty100 oldProperty =   
          ComponentMetaData.CustomPropertyCollection["RaiseErrorOnInvalidValue"];  
        oldValue = (bool)oldProperty.Value;  
        ComponentMetaData.CustomPropertyCollection.RemoveObjectByIndex("RaiseErrorOnInvalidValue");  
      }  
      catch (Exception ex)  
      {  
        // If the old custom property is not available, ignore the error.  
      }  
  
      // Set the value of the new custom property, InvalidValueHandling,  
      //  by using the appropriate enumeration value.  
      IDTSCustomProperty100 newProperty =   
         ComponentMetaData.CustomPropertyCollection["InvalidValueHandling"];  
      if (oldValue == true)  
      {  
        newProperty.Value = InvalidValueHandling.FireError;  
      }  
      else  
      {  
        newProperty.Value = InvalidValueHandling.Ignore;  
      }  
  
    }  
  
    // Update the saved component version metadata to the current version.  
    ComponentMetaData.Version = currentVersion;  
  
  }  
  
}  
```  
  
<span data-ttu-id="8a2c5-123">![Integration Services icono (pequeño)](../../media/dts-16.gif "Icono de Integration Services (pequeño)")  **Manténgase al día con Integration Services**</span><span class="sxs-lookup"><span data-stu-id="8a2c5-123">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="8a2c5-124">Para obtener las descargas, artículos, ejemplos y vídeos más recientes de Microsoft, así como soluciones seleccionadas de la comunidad, visite la página de [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] en MSDN:</span><span class="sxs-lookup"><span data-stu-id="8a2c5-124">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="8a2c5-125">Visite la página de Integration Services en MSDN</span><span class="sxs-lookup"><span data-stu-id="8a2c5-125">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="8a2c5-126">Para recibir notificaciones automáticas de estas actualizaciones, suscríbase a las fuentes RSS disponibles en la página.</span><span class="sxs-lookup"><span data-stu-id="8a2c5-126">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
  
