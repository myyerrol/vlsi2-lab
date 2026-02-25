TOP := croc_soc
SRC := -f croc.f
ARG := --top tb_$(TOP) \
       --binary        \
        -Wno-fatal     \
       --trace         \
       --trace-structs \
        -j 0

.PHONY: comp sim wave clean

comp:
	verilator $(SRC) $(ARG)

sim: comp
	./obj_dir/Vtb_$(TOP)

wave: sim
	gtkwave $(TOP).vcd

clean:
	rm -rf obj_dir $(TOP).vcd
