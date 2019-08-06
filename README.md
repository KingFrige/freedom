Freedom
=======

Run the following commands to clone the repository and get started:

```sh
$ git clone git@github.com:KingFrige/freedom.git
$ cd freedom

#Run this command to update subrepositories used by freedom
$ git submodule update --init --recursive

$ git branch -r

$ git checkout nvdla-fpga-error

$ git config submodule.nvidia-dla-blocks.url git@github.com:KingFrige/block-nvdla-sifive.git
$ git submodule sync

$ git pull origin nvdla-fpga-error
$ git submodule update

$ make -f Makefile.vcu118-iofpga-nvdla verilog
```

Error show
--------------------
```
[info] [0.001] Elaborating design...
mem AXI4-ID <= TL-Source mapping:
	[ 0,  2) <= [128, 132) "MSI Master",
	[ 2,  3) <= [  0,  32) "NVDLA DBB ID#0" [FIFO],
	[ 3,  4) <= [ 32,  64) "NVDLA DBB ID#1" [FIFO],
	[ 4,  5) <= [ 64,  96) "NVDLA DBB ID#2" [FIFO],
	[ 5,  6) <= [ 96, 128) "NVDLA DBB ID#3" [FIFO],
	[ 6,  7) <= [272, 288) "ChipLink Domain #1" [FIFO],
	[ 7,  8) <= [288, 304) "ChipLink Domain #2" [FIFO],
	[ 8,  9) <= [304, 320) "ChipLink Domain #3" [FIFO],
	[ 9, 10) <= [320, 336) "ChipLink Domain #4" [FIFO],
	[10, 11) <= [336, 352) "ChipLink Domain #5" [FIFO],
	[11, 12) <= [352, 368) "ChipLink Domain #6" [FIFO],
	[12, 13) <= [368, 384) "ChipLink Domain #7" [FIFO],
	[13, 21) <= [256, 272) "ChipLink Domain #0" [CACHE]

[error] (run-main-0) java.lang.IllegalArgumentException: requirement failed: nvdla had fifoId Some(1), which was not homogeneous (List((serr,Some(0)), (dtbrom,Some(0)), (island,Some(0)), (nvdla,Some(0)), (nvdla,Some(1)))) 
[error] java.lang.IllegalArgumentException: requirement failed: nvdla had fifoId Some(1), which was not homogeneous (List((serr,Some(0)), (dtbrom,Some(0)), (island,Some(0)), (nvdla,Some(0)), (nvdla,Some(1)))) 
[error] 	at scala.Predef$.require(Predef.scala:277)
[error] 	at freechips.rocketchip.tilelink.TLManagerPortParameters.$anonfun$requireFifo$1(Parameters.scala:97)
[error] 	at freechips.rocketchip.tilelink.TLManagerPortParameters.$anonfun$requireFifo$1$adapted(Parameters.scala:96)
[error] 	at scala.collection.immutable.List.foreach(List.scala:389)
[error] 	at freechips.rocketchip.tilelink.TLManagerPortParameters.requireFifo(Parameters.scala:96)
[error] 	at sifive.blocks.devices.chiplink.ChipLink$$anon$1.<init>(ChipLink.scala:106)
[error] 	at sifive.blocks.devices.chiplink.ChipLink.module$lzycompute(ChipLink.scala:90)
[error] 	at sifive.blocks.devices.chiplink.ChipLink.module(ChipLink.scala:90)
[error] 	at sifive.blocks.devices.chiplink.ChipLink.module(ChipLink.scala:11)
[error] 	at freechips.rocketchip.diplomacy.LazyModuleImpLike.$anonfun$instantiate$2(LazyModule.scala:158)
[error] 	at chisel3.core.Module$.do_apply(Module.scala:49)
```
