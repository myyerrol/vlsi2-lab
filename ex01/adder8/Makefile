.PHONY: comp sim wave clean

SRC := sourcecode/adder8.sv \
       sourcecode/tb_adder8.sv

ARG := --top tb_adder8 \
       --binary        \
        -Wno-fatal     \
       --trace         \
       --trace-structs

comp: $(SRC)
	verilator $(SRC) $(ARG)

sim: comp
	./obj_dir/Vtb_adder8

wave: sim
	gtkwave adder8.vcd

clean:
	rm -rf obj_dir adder8.vcd
