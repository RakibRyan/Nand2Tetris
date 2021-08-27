# Nand2Tetris
Working my way through the <a name="" href="https://www.nand2tetris.org/">Nand2Tetris </a> project &amp; understanding the inner workings of a computer.

This project is from the course [nand2tetris](https://www.nand2tetris.org/). From building logic gates to writing a high level language and an operating system in it, the resultant is a modern-day 16-bit computer which I have documented below. 

<img src="https://static.wixstatic.com/media/44046b_387f62dae530480dac9b1fa8f731bebf~mv2.png/v1/fill/w_415,h_144,al_c,q_85,usm_0.66_1.00_0.01/44046b_387f62dae530480dac9b1fa8f731bebf~mv2.webp" alt="Nand2Tetris image">
<center><text>Building a Modern Computer From First Principles.</text></center>


<h2>Project Outcome</h2>
<ol type="1">
  <li>Bare bones hardware - The _Hack_ computer</li>
  <li>Assembly language - The _Hack_ assembly</li>
  <li>Virtual machine - The _Jack Virtual Machine_ (JVM)</li>
  <li>High level language - The _Jack_ programming language</li>
  <li>Operating System - The _Jack_ OS</li>
</ol> 


## Table of Contents
1. [Hardware](#hardware) 
	- [Logic Gates](#logic-gates)
	- [ALU](#alu)
	- [Registers, RAM, and PC](#registers-ram-and-pc)
2. [Architecture](#architecture)
	- [Instruction Set](#instruction-set)
		- [The A-instruction](#the-a-instruction)
 		- [The C-instruction](#the-c-instruction)
	- [Memory](#memory)
	- [CPU](#cpu)
	- [Computer](#computer)
4. [Assembler](#assembler)
5. [Jack Virtual Machine](#jack-virtual-machine)
	- [The Stack](#the-stack)
	- [Program Control](#program-control)
	- [JVM and Hack](#jvm-and-hack)
6. [Compiler](#compiler)
	- [High Level Language](#high-level-language)
	- [Syntax Analysis](#syntax-analysis)
	- [Code Generation](#code-generation)
7. [Operating System](#operating-system)


# Hardware
This section aims at building the bare-bones of the computer. We first make simple logic gates and then leverage them to further make more sophisticated hardware. The logic is written in a custom Hardware Description Language (HDL) specified [here](https://docs.wixstatic.com/ugd/44046b_2cc5aac034ae49f4bf1650a3d31df32c.pdf).


## Logic Gates
All the logic gates are created from the primitive Nand gate. Here are a list of gates that were implemented.

## Primary
<table>
	<tr>
		<th><a href="./projects/01/Nand2.hdl">Nand</a>
		</th>
		<th><a href="./projects/01/Nor.hdl">Nor</a>
		</th>
		<th><a href="./projects/01/Not.hdl">Not</a>
		</th>
		<th><a href="./projects/01/And.hdl">And</a>
		</th>
		<th><a href="./projects/01/Or.hdl">Or</a>
		</th>
		<th><a href="./projects/01/Xor.hdl">Xor</a>
		</th>
		<th><a href="./projects/01/Xnor.hdl">Xnor</a>
		</th>
	</tr>
	<tr>
		<td><img src="https://github.com/RakibRyan/Nand2Tetris/blob/main/images/nand.png" width="50">
		</td>
		<td><img src="https://github.com/RakibRyan/Nand2Tetris/blob/main/images/nor.png" width="50">
		</td>
		<td><img src="https://github.com/RakibRyan/Nand2Tetris/blob/main/images/not.png" width="50">
		</td>
		<td><img src="https://github.com/RakibRyan/Nand2Tetris/blob/main/images/and.png" width="50">
		</td>
		<td><img src="https://github.com/RakibRyan/Nand2Tetris/blob/main/images/or.png" width="50">
		</td>
		<td><img src="https://github.com/RakibRyan/Nand2Tetris/blob/main/images/xor.png" width="50">
		</td>
		<td><img src="https://github.com/RakibRyan/Nand2Tetris/blob/main/images/xnor.png" width="50">
		</td>
	</tr>
</table>

## Advanced

<table>
	<tr>
		<th><a href="./projects/01/Mux.hdl">Mux</a></th>
		<th><a href="./projects/01/DMux.hdl">DMux</a></th>
	</tr>
	<tr>
		<td><img src="https://github.com/RakibRyan/Nand2Tetris/blob/main/images/Mux.jpg" width="100"></td>
		<td><img src="https://github.com/RakibRyan/Nand2Tetris/blob/main/images/DMux.jpg" width="100"><td>
	</tr>
		
</table>

<table>
	<tr>
		
	</tr>
	<tr>
		
	</tr>
		
</table>


- [Mux](./projects/01/Mux.hdl), [DMux](./projects/01/DMux.hdl)
- [Not16](./projects/01/Not16.hdl), [And16](./projects/01/And16.hdl), [Or16](./projects/01/Or16.hdl), [Mux16](./projects/01/Mux16.hdl) - 16-bit wide gates
- [Or8Way](./projects/01/Or8Way.hdl) - Or(x0,...,x7)
- [Mux4Way16](./projects/01/Mux4Way16.hdl), [Mux8Way16](./projects/01/Mux8Way16.hdl), [DMux4Way16](./projects/01/DMux4Way16.hdl), [DMux8Way16](./projects/01/DMux8Way16.hdl) - 16-bit wide with 4/8 inputs


<h2>Project 1: Gates</h2>
<br>
<ul>
  <li>Primary Logic Gates</li>
</ul>
<br>

<img src="https://www.cloudsavvyit.com/p/uploads/2021/05/22e2d43d.png?width=1198&trim=1,1&bg-color=000&pad=1,1" alt="Primary Gates" width="300">

