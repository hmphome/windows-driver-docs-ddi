---
UID: NA:
---

# Parallel.h header

## -description

This header is used by Parallel Ports. For more information, see
- [Parallel Ports](../_parports/index.md)

Parallel.h contain these programming interfaces:


## Callback functions

| Title   | Description   |
| ---- |:---- |
| [PDETERMINE_IEEE_MODES callback](nc-parallel-pdetermine_ieee_modes.md) | The PDETERMINE_IEEE_MODES-typed callback routine determines which IEEE 1284 protocols a parallel device supports. The system-supplied bus driver for parallel ports supplies this routine. |
| [PNEGOTIATE_IEEE_MODE callback](nc-parallel-pnegotiate_ieee_mode.md) | The PNEGOTIATE_IEEE_MODE-typed callback routine selects the fastest forward and reverse protocols that the system-supplied bus driver for parallel ports supports from among those specified by the caller. |
| [PNEGOTIATE_IEEE_MODE callback](nc-parallel-pnegotiate_ieee_mode~r1.md) | The PNEGOTIATE_IEEE_MODE-typed callback routine selects the fastest forward and reverse protocols that the system-supplied bus driver for parallel ports supports from among those specified by the caller. |
| [PPARALLEL_CLEAR_CHIP_MODE callback](nc-parallel-pparallel_clear_chip_mode.md) | The PPARALLEL_CLEAR_CHIP_MODE-typed callback routine clears the operating mode of a parallel port by resetting the communication mode of the host chipset to IEEE 1284-compatibility mode. |
| [PPARALLEL_DESELECT_ROUTINE callback](nc-parallel-pparallel_deselect_routine.md) | The PPARALLEL_DESELECT_ROUTINE-typed callback routine deselects either an IEEE 1284.3 daisy chain device or an IEEE 1284 end-of-chain device that is attached to a parallel port. |
| [PPARALLEL_FREE_ROUTINE callback](nc-parallel-pparallel_free_routine.md) | The PPARALLEL_FREE_ROUTINE-typed callback routine frees a parallel port. The system-supplied function driver for parallel ports supplies this routine. |
| [PPARALLEL_IEEE_FWD_TO_REV callback](nc-parallel-pparallel_ieee_fwd_to_rev.md) | The PPARALLEL_IEEE_FWD_TO_REV-typed callback routine changes the transfer mode from forward to reverse. The system-supplied bus driver for parallel ports supplies this routine. |
| [PPARALLEL_IEEE_REV_TO_FWD callback](nc-parallel-pparallel_ieee_rev_to_fwd.md) | The PPARALLEL_IEEE_REV_TO_FWD-typed callback routine changes the transfer mode from reverse to forward. The system-supplied bus driver for parallel ports supplies this routine. |
| [PPARALLEL_QUERY_WAITERS_ROUTINE callback](nc-parallel-pparallel_query_waiters_routine.md) | The PPARALLEL_QUERY_WAITERS_ROUTINE-typed callback routine returns the number of IOCTL_INTERNAL_PARALLEL_PORT_ALLOCATE and IOCTL_INTERNAL_SELECT_DEVICE requests that are queued on the work queue of a parallel port. |
| [PPARALLEL_READ callback](nc-parallel-pparallel_read.md) | The PPARALLEL_READ-typed callback routine reads data from a parallel device. The system-supplied bus driver for parallel ports supplies this routine. |
| [PPARALLEL_SET_CHIP_MODE callback](nc-parallel-pparallel_set_chip_mode.md) | The PPARALLEL_SET_CHIP_MODE-typed callback routine sets the operating mode of a parallel port. The system-supplied function driver for parallel ports supplies this routine. |
| [PPARALLEL_TRY_ALLOCATE_ROUTINE callback](nc-parallel-pparallel_try_allocate_routine.md) | The PPARALLEL_TRY_ALLOCATE_ROUTINE-typed (ISR) callback routine attempts to allocate a parallel port at IRQL = DIRQL. The system-supplied function driver for parallel ports supplies this routine. |
| [PPARALLEL_TRY_SELECT_ROUTINE callback](nc-parallel-pparallel_try_select_routine.md) | The PPARALLEL_TRY_SELECT_ROUTINE-typed callback routine selects an IEEE 1284.3 daisy chain device or an IEEE 1284 end-of-chain device that is attached to a parallel port. The system-supplied function driver for parallel ports supplies this routine. |
| [PPARALLEL_WRITE callback](nc-parallel-pparallel_write.md) | The PPARALLEL_WRITE-typed callback routine writes data to a parallel device. The system-supplied bus driver for parallel ports supplies this routine. |
| [PTERMINATE_IEEE_MODE callback](nc-parallel-pterminate_ieee_mode.md) | The PTERMINATE_IEEE_MODE-typed callback routine terminates the current IEEE operating mode and sets the mode to IEEE 1284-compatible. The system-supplied bus driver for parallel ports supplies this routine. |

## Structures

| Title   | Description   |
| ---- |:---- |
| [_MORE_PARALLEL_PORT_INFORMATION structure](ns-parallel-_more_parallel_port_information.md) | The MORE_PARALLEL_PORT_INFORMATION structure specifies information about the system interface that supports the operation of a parallel port. |
| [_PARALLEL_1284_COMMAND structure](ns-parallel-_parallel_1284_command.md) | The PARALLEL_1284_COMMAND structure specifies information that a client uses to select and deselect an IEEE 1284.3 daisy-chain device or an IEEE 1284 end-of-chain device. |
| [_PARALLEL_CHIP_MODE structure](ns-parallel-_parallel_chip_mode.md) | The PARALLEL_CHIP_MODE structure specifies the operating mode of a parallel port. |
| [_PARALLEL_INTERRUPT_INFORMATION structure](ns-parallel-_parallel_interrupt_information.md) | The PARALLEL_INTERRUPT_INFORMATION structure specifies information that a kernel-mode driver can use in the context of an ISR that the driver connects to a parallel port. |
| [_PARALLEL_INTERRUPT_SERVICE_ROUTINE structure](ns-parallel-_parallel_interrupt_service_routine.md) | The PARALLEL_INTERRUPT_SERVICE_ROUTINE structure specifies interrupt services that a kernel-mode driver can connect to the operation of a parallel port. |
| [_PARALLEL_PNP_INFORMATION structure](ns-parallel-_parallel_pnp_information.md) | The PARALLEL_PNP_INFORMATION structure specifies information about the capabilities of a parallel port. |
| [_PARALLEL_PORT_INFORMATION structure](ns-parallel-_parallel_port_information.md) | The PARALLEL_PORT_INFORMATION structure specifies information about the resources assigned to a parallel port, the capabilities of the parallel port, and pointers to callback routines that a kernel-mode driver can use to operate the parallel port. |
| [_PARCLASS_INFORMATION structure](ns-parallel-_parclass_information.md) | The PARCLASS_INFORMATION structure specifies information about a parallel port, pointers to callback routines to operate a parallel port, and pointers to callback routines to read and write to a parallel device. |

## I/O control codes

| Title   | Description   |
| ---- |:---- |
| [IOCTL_INTERNAL_DESELECT_DEVICE IOCTL](ni-parallel-ioctl_internal_deselect_device.md) | The IOCTL_INTERNAL_DESELECT_DEVICE request deselects an IEEE 1284.3 daisy-chain device or an IEEE 1284 end-of-chain device attached to a parallel port. |
| [IOCTL_INTERNAL_DISCONNECT_IDLE IOCTL](ni-parallel-ioctl_internal_disconnect_idle.md) | The IOCTL_INTERNAL_DISCONNECT_IDLE request disconnects the IEEE 1284 operating modes that are set for a parallel device. |
| [IOCTL_INTERNAL_GET_MORE_PARALLEL_PORT_INFO IOCTL](ni-parallel-ioctl_internal_get_more_parallel_port_info.md) | The IOCTL_INTERNAL_GET_MORE_PARALLEL_PORT_INFO request returns information about a parallel port. |
| [IOCTL_INTERNAL_GET_PARALLEL_PNP_INFO IOCTL](ni-parallel-ioctl_internal_get_parallel_pnp_info.md) | The IOCTL_INTERNAL_GET_PARALLEL_PNP_INFO request returns Plug and Play information about a parallel port. |
| [IOCTL_INTERNAL_GET_PARALLEL_PORT_INFO IOCTL](ni-parallel-ioctl_internal_get_parallel_port_info.md) | The IOCTL_INTERNAL_GET_PARALLEL_PORT_INFO request returns information about a parallel port. |
| [IOCTL_INTERNAL_INIT_1284_3_BUS IOCTL](ni-parallel-ioctl_internal_init_1284_3_bus.md) | The IOCTL_INTERNAL_INIT_1284_3_BUS request initializes and assigns an IEEE 1284.3 device ID to all the 1284.3 daisy chain devices that are attached to a parallel port. |
| [IOCTL_INTERNAL_LOCK_PORT IOCTL](ni-parallel-ioctl_internal_lock_port.md) | The IOCTL_INTERNAL_LOCK_PORT request allocates the parallel device's parent parallel port and selects the parallel device on the port. |
| [IOCTL_INTERNAL_LOCK_PORT_NO_SELECT IOCTL](ni-parallel-ioctl_internal_lock_port_no_select.md) | The IOCTL_INTERNAL_LOCK_PORT_NO_SELECT request allocates the parallel device's parent parallel port, but does not select the parallel device. |
| [IOCTL_INTERNAL_PARALLEL_CLEAR_CHIP_MODE IOCTL](ni-parallel-ioctl_internal_parallel_clear_chip_mode.md) | The IOCTL_INTERNAL_PARALLEL_CLEAR_CHIP_MODE request clears the operating mode of a parallel port. |
| [IOCTL_INTERNAL_PARALLEL_CONNECT_INTERRUPT IOCTL](ni-parallel-ioctl_internal_parallel_connect_interrupt.md) | The IOCTL_INTERNAL_PARALLEL_CONNECT_INTERRUPT request connects an optional interrupt service routine and an optional deferred port check routine to a parallel port. |
| [IOCTL_INTERNAL_PARALLEL_DISCONNECT_INTERRUPT IOCTL](ni-parallel-ioctl_internal_parallel_disconnect_interrupt.md) | The IOCTL_INTERNAL_PARALLEL_DISCONNECT_INTERRUPT request disconnects an interrupt service routine (and an optional deferred port check service routine) that was connected by using an IOCTL_INTERNAL_PARALLEL_CONNECT_INTERRUPT request. |
| [IOCTL_INTERNAL_PARALLEL_PORT_ALLOCATE IOCTL](ni-parallel-ioctl_internal_parallel_port_allocate.md) | The IOCTL_INTERNAL_PARALLEL_PORT_ALLOCATE request allocates a parallel port for exclusive access by a client. |
| [IOCTL_INTERNAL_PARALLEL_PORT_FREE IOCTL](ni-parallel-ioctl_internal_parallel_port_free.md) | The IOCTL_INTERNAL_PARALLEL_PORT_FREE request frees a parallel port. |
| [IOCTL_INTERNAL_PARALLEL_SET_CHIP_MODE IOCTL](ni-parallel-ioctl_internal_parallel_set_chip_mode.md) | The IOCTL_INTERNAL_PARALLEL_SET_CHIP_MODE request sets the operating mode of a parallel port. |
| [IOCTL_INTERNAL_PARCLASS_CONNECT IOCTL](ni-parallel-ioctl_internal_parclass_connect.md) | The IOCTL_INTERNAL_PARCLASS_CONNECT request returns information about a parallel port and the callback routines that the system-supplied bus driver for parallel ports provides to operate the parallel port. |
| [IOCTL_INTERNAL_PARCLASS_DISCONNECT IOCTL](ni-parallel-ioctl_internal_parclass_disconnect.md) | The IOCTL_INTERNAL_PARCLASS_DISCONNECT request disconnects a client from a parallel device. |
| [IOCTL_INTERNAL_RELEASE_PARALLEL_PORT_INFO IOCTL](ni-parallel-ioctl_internal_release_parallel_port_info.md) | The IOCTL_INTERNAL_RELEASE_PARALLEL_PORT_INFO request returns STATUS_SUCCESS. |
| [IOCTL_INTERNAL_SELECT_DEVICE IOCTL](ni-parallel-ioctl_internal_select_device.md) | The IOCTL_INTERNAL_SELECT_DEVICE request |
| [IOCTL_INTERNAL_UNLOCK_PORT IOCTL](ni-parallel-ioctl_internal_unlock_port.md) | The IOCTL_INTERNAL_UNLOCK_PORT request deselects a parallel device and frees the parallel device's parent parallel port. |
| [IOCTL_INTERNAL_UNLOCK_PORT_NO_DESELECT IOCTL](ni-parallel-ioctl_internal_unlock_port_no_deselect.md) | The IOCTL_INTERNAL_UNLOCK_PORT_NO_DESELECT request frees a parallel device's parent parallel port. |