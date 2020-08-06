---
title: Habilitar/deshabilitar reescritura (cuadro de diálogo) (Analysis Services-datos multidimensionales) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.partitiondesigner.writebackenabledisable.f1
ms.assetid: 2d254393-3f0d-4b70-8b98-87159f9f3639
author: minewiskan
ms.author: owend
ms.openlocfilehash: 54ee4597ee78f45682730bd0e8d7119d204eaf2b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677922"
---
# <a name="enable-disable-writeback-dialog-box-analysis-services---multidimensional-data"></a>Habilitar/deshabilitar reescritura (cuadro de diálogo) (Analysis Services-datos multidimensionales)
  El cuadro de diálogo **Habilitar/deshabilitar reescritura** permite habilitar o deshabilitar la reescritura para un grupo de medida en un cubo. Al habilitar la reescritura en un grupo de medida se define una partición de reescritura y se crea una tabla de reescritura para ese grupo de medida. Al deshabilitar la reescritura en un grupo de medida se quita la partición de reescritura, pero no se elimina la tabla de reescritura a fin de evitar la pérdida imprevista de datos. Para mostrar el cuadro de diálogo **Habilitar/deshabilitar reescritura** :  
  
-   En el Diseñador de cubos, haga clic en **Configuración de reescritura** (en el panel **Grupos de medida** de la pestaña **Particiones** ).  
  
-   En el Diseñador de cubos, haga clic con el botón derecho en una partición de la cuadrícula **Particiones** (en el panel **Grupos de medida** de la pestaña **Particiones** ) y, después, seleccione **Configuración de reescritura** en el menú contextual.  
  
## <a name="options"></a>Opciones  
 **Nombre de la tabla**  
 Escriba el nombre de la tabla de reescritura que desea crear para la partición seleccionada. La tabla de escritura diferida almacena los cambios realizados al grupo de medidas desde una aplicación cliente.  
  
> [!NOTE]  
>  Esta opción está deshabilitada si la reescritura no está habilitada.  
  
 **Origen de datos**  
 Seleccione el origen de datos que contendrá la tabla de reescritura.  
  
> [!NOTE]  
>  Esta opción está deshabilitada si la reescritura no está habilitada.  
  
 **Nuevo**  
 Haga clic para mostrar el cuadro de diálogo **Administrador de conexiones** y defina un nuevo origen de datos para que contenga la tabla de reescritura.  
  
> [!NOTE]  
>  Esta opción está deshabilitada si la reescritura no está habilitada.  
  
  
