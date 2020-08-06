---
title: Usar anotaciones en paquetes | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- self-documenting packages
- adding annotations
- annotations [Integration Services]
ms.assetid: 48c8ed9a-b10d-490c-9ba7-4b77aa44e3dd
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 27c7df6afd894ea9730027da1d54786ed8397fad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678241"
---
# <a name="use-annotations-in-packages"></a><span data-ttu-id="a6cc6-102">Usar anotaciones en paquetes</span><span class="sxs-lookup"><span data-stu-id="a6cc6-102">Use Annotations in Packages</span></span>
  <span data-ttu-id="a6cc6-103">El Diseñador [!INCLUDE[ssIS](../includes/ssis-md.md)] proporciona anotaciones, que puede usar para que los paquetes se autodocumenten y sean más fáciles de entender y mantener.</span><span class="sxs-lookup"><span data-stu-id="a6cc6-103">The [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer provides annotations, which you can use to make packages self-documenting and easier to understand and maintain.</span></span> <span data-ttu-id="a6cc6-104">Puede agregar anotaciones a las superficies de diseño de flujo de control, flujo de datos y controlador de eventos del Diseñador [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a6cc6-104">You can add annotations to the control flow, data flow, and event handler design surfaces of [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="a6cc6-105">Las anotaciones pueden contener cualquier tipo de texto y resultan útiles para agregar etiquetas, comentarios y demás información descriptiva a un paquete.</span><span class="sxs-lookup"><span data-stu-id="a6cc6-105">The annotations can contain any type of text, and they are useful for adding labels, comments, and other descriptive information to a package.</span></span> <span data-ttu-id="a6cc6-106">Las anotaciones únicamente son una característica de tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="a6cc6-106">Annotations are a design-time feature only.</span></span> <span data-ttu-id="a6cc6-107">Por ejemplo, no se escriben en los registros.</span><span class="sxs-lookup"><span data-stu-id="a6cc6-107">For example, they are not written to logs.</span></span>  
  
 <span data-ttu-id="a6cc6-108">Cuando se presiona ENTRAR, el texto se ajusta a la línea siguiente.</span><span class="sxs-lookup"><span data-stu-id="a6cc6-108">When you press ENTER, the text wraps to the next line.</span></span> <span data-ttu-id="a6cc6-109">El cuadro de anotación aumenta de tamaño automáticamente a medida que agrega líneas de texto adicionales.</span><span class="sxs-lookup"><span data-stu-id="a6cc6-109">The annotation box automatically increases in size as you add additional lines of text.</span></span> <span data-ttu-id="a6cc6-110">Las anotaciones de paquetes se guardan como texto sin cifrar en la sección CDATA del archivo de paquete.</span><span class="sxs-lookup"><span data-stu-id="a6cc6-110">Package annotations are persisted as clear text in the CDATA section of the package file.</span></span>  
  
 <span data-ttu-id="a6cc6-111">Para obtener más información sobre los cambios en el formato del archivo de paquete, vea [Formato de paquetes SSIS](../../2014/integration-services/ssis-package-format.md).</span><span class="sxs-lookup"><span data-stu-id="a6cc6-111">For more information about changes to the format of the package file, see [SSIS Package Format](../../2014/integration-services/ssis-package-format.md).</span></span>  
  
 <span data-ttu-id="a6cc6-112">Cuando se guarda un paquete, el Diseñador [!INCLUDE[ssIS](../includes/ssis-md.md)] guarda las anotaciones en el paquete.</span><span class="sxs-lookup"><span data-stu-id="a6cc6-112">When you save the package, [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer saves the annotations in the package.</span></span>  
  
### <a name="to-add-an-annotation-to-a-package"></a><span data-ttu-id="a6cc6-113">Para agregar una anotación a un paquete</span><span class="sxs-lookup"><span data-stu-id="a6cc6-113">To add an annotation to a package</span></span>  
  
-   [<span data-ttu-id="a6cc6-114">agregar una anotación a un paquete</span><span class="sxs-lookup"><span data-stu-id="a6cc6-114">Add an Annotation to a Package</span></span>](../../2014/integration-services/add-an-annotation-to-a-package.md)  
  
  
