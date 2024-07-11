# FIFO_VerilogHDL
# FIFO Memory Design using Verilog HDL

This project implements a First In First Out (FIFO) memory buffer using Verilog HDL. The design includes combinational and sequential logic to handle data storage and retrieval, ensuring proper management of full and empty states.

## Features

- **FIFO Depth**: 16 entries
- **Data Width**: 8 bits
- **Full and Empty Flag Management**: Properly handles full and empty states
- **Read and Write Operations**: Synchronized with a clock signal

## Design Details

### Module Parameters

- `DATA_WIDTH`: Width of the data (default: 8)
- `FIFO_DEPTH`: Depth of the FIFO (default: 16)
- `ADDR_WIDTH`: Address width, calculated as log2(FIFO_DEPTH) (default: 4)

### Inputs and Outputs

- **Inputs**
  - `clk`: Clock input
  - `reset`: Reset input
  - `wr_en`: Write enable signal
  - `rd_en`: Read enable signal
  - `wr_data`: Data to be written to the FIFO

- **Outputs**
  - `rd_data`: Data read from the FIFO
  - `full`: Flag indicating the FIFO is full
  - `empty`: Flag indicating the FIFO is empty

## Code Explanation

### Write Operation

The write operation is performed on the positive edge of the clock. If the write enable signal (`wr_en`) is asserted and the FIFO is not full, data is written to the FIFO, and the write pointer (`wr_ptr`) is incremented.

### Read Operation

The read operation is performed on the positive edge of the clock. If the read enable signal (`rd_en`) is asserted and the FIFO is not empty, data is read from the FIFO, and the read pointer (`rd_ptr`) is incremented.

### FIFO Full and Empty Status

The full and empty status of the FIFO is managed based on the FIFO count (`fifo_count`). The FIFO is full when the count equals the FIFO depth, and it is empty when the count is zero.

