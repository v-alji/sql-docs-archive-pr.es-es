---
title: Seleccionar dispositivo de copia de seguridad | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
f1_keywords:
- sql12.swb.selectbackupdevice.f1
ms.assetid: 7887c9fd-15ce-4cc8-b069-845c1d09088c
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8a848f9188eec0ebb09931bca460b0389b9570ff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87748136"
---
# <a name="select-backup-device"></a><span data-ttu-id="99b1a-102">Seleccionar dispositivo de copia de seguridad</span><span class="sxs-lookup"><span data-stu-id="99b1a-102">Select Backup Device</span></span>
  <span data-ttu-id="99b1a-103">Utilice el cuadro de diálogo **Seleccionar dispositivo lógico de copia de seguridad** para seleccionar un dispositivo de copia de seguridad para la operación de restauración.</span><span class="sxs-lookup"><span data-stu-id="99b1a-103">Use the **Select Backup Device** dialog box to select a logical backup device for the restore operation.</span></span>  
  
 <span data-ttu-id="99b1a-104">Un dispositivo lógico de copia de seguridad es un dispositivo lógico definido por el usuario que corresponde a un dispositivo físico, ya sea una unidad de cinta o de disco, que proporciona el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="99b1a-104">A logical backup device is a user-defined logical device that corresponds to a physical device, either a tape drive or a disk drive, that is provided by the operating system.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="99b1a-105">Si una copia de seguridad utiliza varios dispositivos de copia de seguridad, todos deben corresponder a un solo tipo de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="99b1a-105">If a backup uses multiple backup devices, they all must correspond to a single type of device.</span></span>  
  
 <span data-ttu-id="99b1a-106">**Para utilizar SQL Server Management Studio a fin de ver el contenido de un dispositivo de copia de seguridad**</span><span class="sxs-lookup"><span data-stu-id="99b1a-106">**To use SQL Server Management Studio to view the contents of a backup device**</span></span>  
  
-   [<span data-ttu-id="99b1a-107">Ver el contenido de una cinta o un archivo de copia de seguridad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="99b1a-107">View the Contents of a Backup Tape or File &#40;SQL Server&#41;</span></span>](view-the-contents-of-a-backup-tape-or-file-sql-server.md)  
  
-   [<span data-ttu-id="99b1a-108">Ver las propiedades y el contenido de un dispositivo lógico de copia de seguridad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="99b1a-108">View the Properties and Contents of a Logical Backup Device &#40;SQL Server&#41;</span></span>](view-the-properties-and-contents-of-a-logical-backup-device-sql-server.md)  
  
## <a name="options"></a><span data-ttu-id="99b1a-109">Opciones</span><span class="sxs-lookup"><span data-stu-id="99b1a-109">Options</span></span>  
 <span data-ttu-id="99b1a-110">**Dispositivo de copia de seguridad**</span><span class="sxs-lookup"><span data-stu-id="99b1a-110">**Backup device**</span></span>  
 <span data-ttu-id="99b1a-111">En el cuadro de lista, seleccione el nombre de un dispositivo lógico de copia de seguridad desde el que desea efectuar la restauración.</span><span class="sxs-lookup"><span data-stu-id="99b1a-111">In the list box, select the name of a logical backup device from which you want to restore.</span></span>  
  
 <span data-ttu-id="99b1a-112">Para obtener información sobre cómo ver el contenido de un dispositivo de copia de seguridad, vea [Ver las propiedades y el contenido de un dispositivo lógico de copia de seguridad &#40;SQL Server&#41;](view-the-properties-and-contents-of-a-logical-backup-device-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="99b1a-112">For information about how to view the contents of a backup device, see [View the Properties and Contents of a Logical Backup Device &#40;SQL Server&#41;](view-the-properties-and-contents-of-a-logical-backup-device-sql-server.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="99b1a-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="99b1a-113">Remarks</span></span>  
 <span data-ttu-id="99b1a-114">Si no ve un dispositivo lógico de copia de seguridad que contenga la copia de seguridad que busca en la lista, puede que dicha copia de seguridad se haya escrito directamente en uno o varios archivos o unidades de cinta.</span><span class="sxs-lookup"><span data-stu-id="99b1a-114">If you do not see a logical backup device that contains the backup you are seeking on the list, the backup might have been written directly to one or more files or tape drives.</span></span> <span data-ttu-id="99b1a-115">Si es así, cancele el cuadro de diálogo **Seleccionar dispositivo de copia de seguridad** ; en el cuadro de diálogo **Especificar copia de seguridad** , seleccione **Archivo** o **Cinta** en el cuadro de lista **Medio para copia de seguridad** .</span><span class="sxs-lookup"><span data-stu-id="99b1a-115">If this is the case, cancel the **Select Backup Device** dialog box; and in the **Specify Backup** dialog box, select **File** or **Tape** in the **Backup media** list box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99b1a-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="99b1a-116">See Also</span></span>  
 [<span data-ttu-id="99b1a-117">Dispositivos de copia de seguridad &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="99b1a-117">Backup Devices &#40;SQL Server&#41;</span></span>](backup-devices-sql-server.md)  
  
  
