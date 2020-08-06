---
title: Objeto SqlXmlAdapter (clases administradas de SQLXML) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- void Update(DataSet ds) method
- SqlXmlAdapter object
- void Fill(DataSet ds) method
- SQLXML Managed Classes, SqlXmlAdapter object
- Managed Classes [SQLXML], SqlXmlAdapter object
ms.assetid: 0a16eddf-fc26-4d92-82d4-359b5fb905d5
author: rothja
ms.author: jroth
ms.openlocfilehash: 1357ab7d070c7c2e451e31bccfda22c58eac42d5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87662764"
---
# <a name="sqlxmladapter-object-sqlxml-managed-classes"></a><span data-ttu-id="0634a-102">Objeto SqlXmlAdapter (clases administradas SQLXML)</span><span class="sxs-lookup"><span data-stu-id="0634a-102">SqlXmlAdapter Object (SQLXML Managed Classes)</span></span>
  <span data-ttu-id="0634a-103">Este objeto proporciona métodos que facilitan la interacción con el conjunto de datos de [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0634a-103">This object provides methods that facilitate interaction with the dataset in the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework.</span></span> <span data-ttu-id="0634a-104">Para obtener un ejemplo funcional, vea [obtener acceso a la funcionalidad de SQLXML en el entorno de .net](accessing-sqlxml-functionality-in-the-net-environment.md).</span><span class="sxs-lookup"><span data-stu-id="0634a-104">For a working sample, see [Accessing SQLXML Functionality in the .NET Environment](accessing-sqlxml-functionality-in-the-net-environment.md).</span></span>  
  
 <span data-ttu-id="0634a-105">El objeto SqlXmlAdapter admite estos métodos:</span><span class="sxs-lookup"><span data-stu-id="0634a-105">The SqlXmlAdapter object supports these methods:</span></span>  
  
 <span data-ttu-id="0634a-106">void Fill (DataSet DS)</span><span class="sxs-lookup"><span data-stu-id="0634a-106">void Fill(DataSet ds)</span></span>  
 <span data-ttu-id="0634a-107">Rellena el conjunto de datos de .NET Framework con los datos XML recuperados de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0634a-107">Fills the dataset in the .NET Framework with the XML data retrieved from [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="0634a-108">void Update (DataSet DS)</span><span class="sxs-lookup"><span data-stu-id="0634a-108">void Update(DataSet ds)</span></span>  
 <span data-ttu-id="0634a-109">Aplica actualizaciones a los registros de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] a partir de los datos del conjunto de datos.</span><span class="sxs-lookup"><span data-stu-id="0634a-109">Applies updates to records in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] from the data in the dataset.</span></span>  
  
 <span data-ttu-id="0634a-110">El objeto SqlXmlAdapter admite estos constructores:</span><span class="sxs-lookup"><span data-stu-id="0634a-110">The SqlXmlAdapter object supports these constructors:</span></span>  
  
```  
public SqlXmlAdapter(SqlXmlCommand  cmd)   
  
public SqlXmlAdapter(  
                     string commandText,   
                     SqlXmlCommandType cmdType,   
                     string connectionString  
                      )   
  
public SqlXmlAdapter(  
                     Stream commandStream,   
                     SqlXmlCommandType cmdType,   
                     string connectionString  
                     )   
```  
  
## <a name="see-also"></a><span data-ttu-id="0634a-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0634a-111">See Also</span></span>  
 <span data-ttu-id="0634a-112">[Objeto SqlXmlCommand &#40;clases administradas de SQLXML&#41;](sqlxml-4-0-net-framework-support-managed-classes.md) </span><span class="sxs-lookup"><span data-stu-id="0634a-112">[SqlXmlCommand Object &#40;SQLXML Managed Classes&#41;](sqlxml-4-0-net-framework-support-managed-classes.md) </span></span>  
 [<span data-ttu-id="0634a-113">Objeto SqlXmlParameter &#40;clases administradas de SQLXML&#41;</span><span class="sxs-lookup"><span data-stu-id="0634a-113">SqlXmlParameter Object &#40;SQLXML Managed Classes&#41;</span></span>](sqlxml-managed-classes-sqlxmlparameter-object.md)  
  
  
