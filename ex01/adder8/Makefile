TOP := adder8
SRC := sourcecode/$(TOP).sv \
       sourcecode/tb_$(TOP).sv
ARG := --top tb_$(TOP) \
       --binary        \
        -Wno-fatal     \
       --trace         \
       --trace-structs

.PHONY: comp sim wave clean

comp: $(SRC)
	verilator $(SRC) $(ARG)

sim: comp
	./obj_dir/Vtb_$(TOP)

wave: sim
	gtkwave $(TOP).vcd

clean:
	rm -rf obj_dir $(TOP).vcd
