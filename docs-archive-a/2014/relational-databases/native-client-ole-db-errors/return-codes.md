---
title: Códigos de retorno | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- OLE DB error handling, return codes
- SQL Server Native Client OLE DB provider, errors
- failed function [OLE DB]
- successful function [OLE DB]
- S_FALSE
- IS_ERROR macro
- DB_S_ERRORSOCCURRED return
- return codes [OLE DB]
- S_OK
- FAILED macro
- errors [OLE DB], return codes
ms.assetid: 7f7457e9-fce4-400c-82e5-ee02e9e811c6
author: rothja
ms.author: jroth
ms.openlocfilehash: dd033d16b1e95773d2cab1c4e1fca733dc491b96
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87675834"
---
# <a name="return-codes"></a><span data-ttu-id="dac79-102">Códigos de retorno</span><span class="sxs-lookup"><span data-stu-id="dac79-102">Return Codes</span></span>
  <span data-ttu-id="dac79-103">En el nivel más básico, una función miembro se ejecuta correctamente o genera un error.</span><span class="sxs-lookup"><span data-stu-id="dac79-103">At the most basic level, a member function either succeeds or fails.</span></span> <span data-ttu-id="dac79-104">En un nivel algo más preciso, puede que una función se ejecute correctamente pero que el resultado no sea el que esperaba el programador de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="dac79-104">At a somewhat more precise level, a function can succeed, but its success may not be what the application developer intended.</span></span>  
  
 <span data-ttu-id="dac79-105">Para obtener más información sobre los códigos de retorno OLE DB, vea [Códigos de retorno (OLE DB)](https://go.microsoft.com/fwlink/?LinkId=101631).</span><span class="sxs-lookup"><span data-stu-id="dac79-105">For more information about OLE DB return codes, see [Return Codes (OLE DB)](https://go.microsoft.com/fwlink/?LinkId=101631).</span></span>  
  
 <span data-ttu-id="dac79-106">Cuando una [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] función miembro de proveedor de OLE DB de Native Client devuelve S_OK, la función se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="dac79-106">When a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider member function returns S_OK, the function succeeded.</span></span>  
  
 <span data-ttu-id="dac79-107">Cuando una [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] función miembro de proveedor de OLE DB de Native Client no devuelve S_OK, se produce un error en el desempaquetado de HRESULT de OLE/com y IS_ERROR macros pueden determinar el éxito o el error general de una función.</span><span class="sxs-lookup"><span data-stu-id="dac79-107">When a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider member function does not return S_OK, the OLE/COM HRESULT-unpacking FAILED and IS_ERROR macros can determine the overall success or failure of a function.</span></span>  
  
 <span data-ttu-id="dac79-108">Si FAILed o IS_ERROR devuelve TRUE, el [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] consumidor del proveedor de OLE DB de Native Client está seguro de que se ha producido un error en la ejecución de la función miembro.</span><span class="sxs-lookup"><span data-stu-id="dac79-108">If FAILED or IS_ERROR returns TRUE, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider consumer is assured that member function execution failed.</span></span> <span data-ttu-id="dac79-109">Cuando FAILed o IS_ERROR devuelven FALSE y HRESULT no es igual a S_OK, el [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] consumidor del proveedor de OLE DB de Native Client está seguro de que la función se realizó correctamente en algún sentido.</span><span class="sxs-lookup"><span data-stu-id="dac79-109">When FAILED or IS_ERROR return FALSE and the HRESULT does not equal S_OK, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider consumer is assured that the function succeeded in some sense.</span></span> <span data-ttu-id="dac79-110">El consumidor puede recuperar información detallada sobre este valor "éxito con información" de las [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] interfaces de error del proveedor de OLE DB de Native Client.</span><span class="sxs-lookup"><span data-stu-id="dac79-110">The consumer can retrieve detailed information on this "success with information" return from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider error interfaces.</span></span> <span data-ttu-id="dac79-111">Además, en el caso de que se produzca un error claramente en una función (la macro FAILed devuelve TRUE), la información de error ampliada está disponible en las [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] interfaces de error del proveedor de OLE DB de Native Client.</span><span class="sxs-lookup"><span data-stu-id="dac79-111">Also, in the case where a function clearly fails (the FAILED macro returns TRUE), extended error information is available from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider error interfaces.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="dac79-112">Los consumidores de proveedores de OLE DB de Native Client suelen encontrar el valor devuelto por el DB_S_ERRORSOCCURRED "success with Information".</span><span class="sxs-lookup"><span data-stu-id="dac79-112">Native Client OLE DB provider consumers commonly encounter the DB_S_ERRORSOCCURRED "success with information" HRESULT return.</span></span> <span data-ttu-id="dac79-113">Normalmente, las funciones miembro que devuelven DB_S_ERRORSOCCURRED definen uno o más parámetros que proporcionen valores de estado al consumidor.</span><span class="sxs-lookup"><span data-stu-id="dac79-113">Typically, member functions that return DB_S_ERRORSOCCURRED define one or more parameters that deliver status values to the consumer.</span></span> <span data-ttu-id="dac79-114">Es posible que no haya más información de error disponible para el consumidor que los parámetros de valor de estado devueltos, de modo que los consumidores deban implementar la lógica de la aplicación para recuperar los valores de estado cuando estén disponibles.</span><span class="sxs-lookup"><span data-stu-id="dac79-114">No error information may be available to the consumer other than that returned in status-value parameters, so consumers should implement application logic to retrieve status values when they are available.</span></span>  
  
 <span data-ttu-id="dac79-115">Las [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] funciones miembro del proveedor de OLE DB de Native Client no devuelven el código de éxito S_FALSE.</span><span class="sxs-lookup"><span data-stu-id="dac79-115">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider member functions do not return the success code S_FALSE.</span></span> <span data-ttu-id="dac79-116">Todas [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] las funciones miembro de proveedor de OLE DB de Native Client siempre devuelven S_OK para indicar que se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="dac79-116">All [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider member functions always return S_OK to indicate success.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dac79-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="dac79-117">See Also</span></span>  
 [<span data-ttu-id="dac79-118">Errores</span><span class="sxs-lookup"><span data-stu-id="dac79-118">Errors</span></span>](errors.md)  
  
  
