Usage:
1. Generate a target-scoped FIFO of block memory for internal health and status usage. Specify the data type as the HealthAndStatusUpdate cluster. Specify never arbitrate for read and always arbitrate for write.
2. Generate a host to target - DMA FIFO for query communications. Specify the data type as U64. Specify never arbitrate for read.
3. Generate a target to host - DMA FIFO for query responses. Specify the data type as U32. Specify never arbitrate for read.
4. Generate a memory block for health and status storage in the FPGA. Specify the data type as U32.
5. Drop the HealthAndStatus.vi into your main FPGA vi, link up the created FIFO's and memory blocks.
5. Use the internal health and status FIFO for creating update requests which are processed by the ProcessHealthAndStatusUpdates.vi. It is recommended to create a helper VI for putting the health and status update data onto the FIFO. One is provided in the library, it is called UpdateHealthAndStatus.vi.


