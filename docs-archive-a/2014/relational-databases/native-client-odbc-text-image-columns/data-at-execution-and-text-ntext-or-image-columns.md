---
title: Columnas de datos en ejecución y Text, ntext o Image | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- text columns [ODBC]
- SQL Server Native Client ODBC driver, image columns
- SQL Server Native Client ODBC driver, text columns
- data types [ODBC], image
- data types [ODBC], text
- columns [ODBC]
- ODBC data types, image columns
- ODBC data types, text columns
- data-at-execution
- ODBC data-at-execution
- image columns [ODBC]
ms.assetid: 67ffb1a6-f38d-4712-ba64-96bdd41ec2b2
author: rothja
ms.author: jroth
ms.openlocfilehash: 404fade34862fe4705ec440eef7f466a9073250b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87750858"
---
# <a name="data-at-execution-and-text-ntext-or-image-columns"></a><span data-ttu-id="79379-102">Datos en ejecución y columnas de tipo text, ntext o image</span><span class="sxs-lookup"><span data-stu-id="79379-102">Data-at-Execution and Text, ntext, or Image Columns</span></span>
  <span data-ttu-id="79379-103">Datos en ejecución de ODBC es una característica que habilita a las aplicaciones para trabajar con grandes volúmenes de datos en columnas o parámetros enlazados.</span><span class="sxs-lookup"><span data-stu-id="79379-103">ODBC data-at-execution is a feature that enables applications to work with extremely large amounts of data on bound columns or parameters.</span></span> <span data-ttu-id="79379-104">Al recuperar columnas **Text**, **ntext**o **Image** muy grandes, es posible que una aplicación no pueda asignar simplemente un búfer enorme, enlazar la columna al búfer y capturar la fila.</span><span class="sxs-lookup"><span data-stu-id="79379-104">When retrieving very large **text**, **ntext**, or **image** columns, an application may not be able to simply allocate a huge buffer, bind the column into the buffer, and fetch the row.</span></span> <span data-ttu-id="79379-105">Al actualizar columnas **Text**, **ntext**o **Image** muy grandes, es posible que la aplicación no pueda asignar simplemente un búfer enorme, enlazarlo a un marcador de parámetro en una instrucción SQL y, a continuación, ejecutar la instrucción.</span><span class="sxs-lookup"><span data-stu-id="79379-105">When updating very large **text**, **ntext**, or **image** columns, the application might not be able to simply allocate a huge buffer, bind it to a parameter marker in an SQL statement, and then execute the statement.</span></span> <span data-ttu-id="79379-106">En estos casos, la aplicación debe utilizar [SQLGetData](../native-client-odbc-api/sqlgetdata.md) o [SQLPutData](../native-client-odbc-api/sqlputdata.md) con sus opciones de datos en ejecución.</span><span class="sxs-lookup"><span data-stu-id="79379-106">In these cases, the application must use [SQLGetData](../native-client-odbc-api/sqlgetdata.md) or [SQLPutData](../native-client-odbc-api/sqlputdata.md) with its data-at-execution options.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79379-107">Consulte también</span><span class="sxs-lookup"><span data-stu-id="79379-107">See Also</span></span>  
 [<span data-ttu-id="79379-108">Administrar columnas de texto e imagen</span><span class="sxs-lookup"><span data-stu-id="79379-108">Managing Text and Image Columns</span></span>](managing-text-and-image-columns.md)  
  
  
