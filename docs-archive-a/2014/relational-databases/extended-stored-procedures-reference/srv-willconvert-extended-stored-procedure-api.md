---
title: srv_willconvert (API de procedimiento almacenado extendido) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_willconvert
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_willconvert
ms.assetid: 6f4db5fd-215a-461c-95e4-17697852733e
author: rothja
ms.author: jroth
ms.openlocfilehash: 0b9adfbd2a73b30cbfc0229b7942f79d3ddc1a82
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751010"
---
# <a name="srv_willconvert-extended-stored-procedure-api"></a><span data-ttu-id="57acb-102">srv_willconvert (API de procedimiento almacenado extendido)</span><span class="sxs-lookup"><span data-stu-id="57acb-102">srv_willconvert (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="57acb-103">Use la integración con CLR en su lugar.</span><span class="sxs-lookup"><span data-stu-id="57acb-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="57acb-104">Determina si está disponible una conversión de tipos de datos concreta en la Biblioteca ODS.</span><span class="sxs-lookup"><span data-stu-id="57acb-104">Determines whether a specific data type conversion is available within the ODS Library.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57acb-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="57acb-105">Syntax</span></span>  
  
```  
  
BOOL srv_willconvert (  
int  
srctype  
,  
int  
desttype   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="57acb-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="57acb-106">Arguments</span></span>  
 <span data-ttu-id="57acb-107">*srctype*</span><span class="sxs-lookup"><span data-stu-id="57acb-107">*srctype*</span></span>  
 <span data-ttu-id="57acb-108">Indica el tipo de los datos que se van a convertir.</span><span class="sxs-lookup"><span data-stu-id="57acb-108">Indicates the data type of the data to be converted.</span></span> <span data-ttu-id="57acb-109">Este parámetro puede ser cualquiera de los tipos de datos de la API Procedimiento almacenado extendido.</span><span class="sxs-lookup"><span data-stu-id="57acb-109">This parameter can be any of the Extended Stored Procedure API data types.</span></span>  
  
 <span data-ttu-id="57acb-110">*desttype*</span><span class="sxs-lookup"><span data-stu-id="57acb-110">*desttype*</span></span>  
 <span data-ttu-id="57acb-111">Indica el tipo de datos al que se convierten los datos de origen.</span><span class="sxs-lookup"><span data-stu-id="57acb-111">Indicates the data type to which the source data is converted.</span></span> <span data-ttu-id="57acb-112">Este parámetro puede ser cualquiera de los tipos de datos de la API Procedimiento almacenado extendido.</span><span class="sxs-lookup"><span data-stu-id="57acb-112">This parameter can be any of the Extended Stored Procedure API data types.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="57acb-113">Devoluciones</span><span class="sxs-lookup"><span data-stu-id="57acb-113">Returns</span></span>  
 <span data-ttu-id="57acb-114">TRUE si se admite la conversión del tipo de datos; FALSE si no se admite la conversión del tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="57acb-114">TRUE if the data type conversion is supported; FALSE if the data type conversion is not supported.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="57acb-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="57acb-115">Remarks</span></span>  
 <span data-ttu-id="57acb-116">Para obtener una descripción de cada tipo de datos, vea [Data Types &#40;Extended Stored Procedure API&#41;](data-types-extended-stored-procedure-api.md) (Tipos de datos &#40;API de procedimiento almacenado extendido&#41;).</span><span class="sxs-lookup"><span data-stu-id="57acb-116">For a description of each data type, see [Data Types &#40;Extended Stored Procedure API&#41;](data-types-extended-stored-procedure-api.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="57acb-117">Debe revisar minuciosamente el código fuente de los procedimientos almacenados extendidos y debe probar las DLL compiladas antes de instalarlas en el servidor de producción.</span><span class="sxs-lookup"><span data-stu-id="57acb-117">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="57acb-118">Para obtener información acerca de la revisión y pruebas de seguridad, vea este [sitio web de Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="57acb-118">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57acb-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="57acb-119">See Also</span></span>  
 [<span data-ttu-id="57acb-120">srv_convert &#40;API de procedimiento almacenado extendido&#41;</span><span class="sxs-lookup"><span data-stu-id="57acb-120">srv_convert &#40;Extended Stored Procedure API&#41;</span></span>](srv-convert-extended-stored-procedure-api.md)  
  
  
