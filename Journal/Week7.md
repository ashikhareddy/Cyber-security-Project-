In week 7, we again started working on the network design because our mentor was not satisfied with our previous design. After checking the feedback carefully, we realised that our diagram was not clear enough.

During the break week, we had a meeting where we discussed our overall progress and what changes need to be done. We mainly focused on understanding the feedback and identifying the mistakes in our design.

Today, we met at the university and worked together on improving the network design. Everyone contributed their ideas and we tried to fix the issues step by step. We looked back at the feedback and reviewed all the comments given by the mentor, and based on that we started making changes in the diagram.We focused more on improving the structure, making the connections clear, and correcting the data flow. This time, our main goal is to make sure the design is clear, properly structured, and meets the mentor’s expectations.

Following up on the meeting we have curated a network design which is the most simplest WAN with covering all the concepts of what we have learnt so far.
Below we have pasted the design of the network. we have also provided the file below it so you can open it in draw.io and see the full design properly. This design took lots of meetings, trial and errors.

Design 1- 

<img width="1027" height="913" alt="Screenshot 2026-04-27 211440" src="https://github.com/user-attachments/assets/91c0aa5c-1fcf-4d65-83d2-93d872771ac4" />


Please click this link to access the file -> [MMHN_Network_Design.drawio](https://github.com/user-attachments/files/27123787/MMHN_Network_Design.drawio)
<mxfile host="app.diagrams.net">
  <diagram id="u0E5gDnnksihhXm-GPRx" name="Page-1">
    <mxGraphModel dx="1667" dy="2811" grid="1" gridSize="10" guides="1" tooltips="1" connect="1" arrows="1" fold="1" page="1" pageScale="1" pageWidth="1400" pageHeight="2000" math="0" shadow="0">
      <root>
        <mxCell id="0" />
        <mxCell id="1" parent="0" />
        <mxCell id="title" parent="1" style="text;html=1;strokeColor=none;fillColor=none;align=center;verticalAlign=middle;whiteSpace=wrap;rounded=0;fontSize=20;fontStyle=1;fontColor=#1e3a5f;" value="Melbourne Metro Health Network (MMHN)" vertex="1">
          <mxGeometry height="36" width="1000" x="164" y="-193" as="geometry" />
        </mxCell>
        <mxCell id="isp_router" parent="1" style="shape=mxgraph.cisco.routers.router;html=1;pointerEvents=1;dashed=0;fillColor=#dae8fc;strokeColor=#6c8ebf;strokeWidth=2;verticalLabelPosition=bottom;verticalAlign=top;align=center;outlineConnect=0;fontSize=11;fontStyle=0;" value="" vertex="1">
          <mxGeometry height="70" width="80" x="565" y="10" as="geometry" />
        </mxCell>
        <mxCell id="e_internet_isp" edge="1" parent="1" source="OJkc2mzw6svLMNVJvNq--21" style="edgeStyle=orthogonalEdgeStyle;html=1;entryX=0.5;entryY=0;entryDx=0;entryDy=0;strokeColor=#666666;strokeWidth=2;endArrow=none;startArrow=none;endFill=0;startFill=0;" target="isp_router" value="">
          <mxGeometry relative="1" as="geometry">
            <mxPoint x="605" y="-42" as="sourcePoint" />
          </mxGeometry>
        </mxCell>
        <mxCell id="lbl_internet_isp" parent="1" style="text;html=1;strokeColor=none;fillColor=none;align=left;verticalAlign=middle;whiteSpace=wrap;rounded=0;fontSize=10;fontColor=#666666;" value="Public internet link" vertex="1">
          <mxGeometry height="20" width="140" x="605" y="-42" as="geometry" />
        </mxCell>
        <mxCell id="OJkc2mzw6svLMNVJvNq--5" edge="1" parent="1" source="OJkc2mzw6svLMNVJvNq--22" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;curved=1;dashed=1;dashPattern=12 12;strokeColor=light-dark(#000000,#FFB400);endArrow=none;endFill=0;" target="router_a">
          <mxGeometry relative="1" as="geometry">
            <Array as="points">
              <mxPoint x="606" y="340" />
              <mxPoint x="205" y="340" />
            </Array>
            <mxPoint x="605" y="240" as="sourcePoint" />
          </mxGeometry>
        </mxCell>
        <mxCell id="OJkc2mzw6svLMNVJvNq--6" edge="1" parent="1" source="OJkc2mzw6svLMNVJvNq--22" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;curved=1;dashed=1;dashPattern=12 12;strokeColor=light-dark(#000000,#FFB400);endArrow=none;endFill=0;exitX=0.5;exitY=1;exitDx=0;exitDy=0;" target="router_b">
          <mxGeometry relative="1" as="geometry">
            <mxPoint x="605" y="240" as="sourcePoint" />
          </mxGeometry>
        </mxCell>
        <mxCell id="OJkc2mzw6svLMNVJvNq--7" edge="1" parent="1" source="OJkc2mzw6svLMNVJvNq--22" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;exitX=0.5;exitY=1;exitDx=0;exitDy=0;curved=1;dashed=1;dashPattern=12 12;strokeColor=light-dark(#000000,#FFB400);endArrow=none;endFill=0;" target="router_c">
          <mxGeometry relative="1" as="geometry">
            <Array as="points">
              <mxPoint x="606" y="360" />
              <mxPoint x="1175" y="360" />
            </Array>
            <mxPoint x="605" y="240" as="sourcePoint" />
          </mxGeometry>
        </mxCell>
        <mxCell id="OJkc2mzw6svLMNVJvNq--10" edge="1" parent="1" style="edgeStyle=orthogonalEdgeStyle;curved=1;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;exitX=0;exitY=0.5;exitDx=0;exitDy=0;entryX=1;entryY=0.5;entryDx=0;entryDy=0;endArrow=none;endFill=0;" target="OJkc2mzw6svLMNVJvNq--9">
          <mxGeometry relative="1" as="geometry">
            <mxPoint x="555" y="195" as="sourcePoint" />
          </mxGeometry>
        </mxCell>
        <mxCell id="e_isp_fw" edge="1" parent="1" source="isp_router" style="edgeStyle=orthogonalEdgeStyle;html=1;exitX=0.5;exitY=1;exitDx=0;exitDy=0;entryX=0.5;entryY=0;entryDx=0;entryDy=0;strokeColor=#b85450;strokeWidth=2.5;endArrow=none;startArrow=none;endFill=0;startFill=0;" value="">
          <mxGeometry relative="1" as="geometry">
            <mxPoint x="605" y="150" as="targetPoint" />
          </mxGeometry>
        </mxCell>
        <mxCell id="lbl_isp_fw" parent="1" style="text;html=1;strokeColor=none;fillColor=none;align=left;verticalAlign=middle;whiteSpace=wrap;rounded=0;fontSize=10;fontColor=#b85450;" value="WAN uplink&#xa;(internet traffic only)" vertex="1">
          <mxGeometry height="30" width="160" x="615" y="98" as="geometry" />
        </mxCell>
        <mxCell id="e_fw_server" edge="1" parent="1" style="edgeStyle=orthogonalEdgeStyle;html=1;exitX=1;exitY=0.5;exitDx=0;exitDy=0;strokeColor=#9673a6;strokeWidth=2;endArrow=none;startArrow=none;endFill=0;startFill=0;" target="OJkc2mzw6svLMNVJvNq--23" value="">
          <mxGeometry relative="1" as="geometry">
            <mxPoint x="655" y="195" as="sourcePoint" />
            <mxPoint x="830" y="194" as="targetPoint" />
          </mxGeometry>
        </mxCell>
        <mxCell id="lbl_fw_server" parent="1" style="text;html=1;strokeColor=none;fillColor=none;align=center;verticalAlign=middle;whiteSpace=wrap;rounded=0;fontSize=9;fontColor=#9673a6;" value="Internal interface&#xa;Direct access — no internet involved" vertex="1">
          <mxGeometry height="30" width="168" x="662" y="160" as="geometry" />
        </mxCell>
        <mxCell id="campus_a_box" parent="1" style="rounded=1;whiteSpace=wrap;html=1;fillColor=none;strokeColor=#6c8ebf;strokeWidth=2;dashed=1;dashPattern=8 4;verticalAlign=top;fontSize=13;fontStyle=1;fontColor=#1e3a5f;arcSize=3;" value="Hospital A - Clayton Campus" vertex="1">
          <mxGeometry height="600" width="330" x="60" y="560" as="geometry" />
        </mxCell>
        <mxCell id="router_a" parent="1" style="shape=mxgraph.cisco.routers.router;html=1;pointerEvents=1;dashed=0;fillColor=#dae8fc;strokeColor=#6c8ebf;strokeWidth=2;verticalLabelPosition=bottom;verticalAlign=top;align=center;outlineConnect=0;fontSize=11;" value="" vertex="1">
          <mxGeometry height="70" width="80" x="165" y="590" as="geometry" />
        </mxCell>
        <mxCell id="e_ra_swa" edge="1" parent="1" source="router_a" style="edgeStyle=orthogonalEdgeStyle;html=1;exitX=0.5;exitY=1;exitDx=0;exitDy=0;entryX=0.5;entryY=0;entryDx=0;entryDy=0;strokeColor=#82b366;strokeWidth=2;endArrow=block;startArrow=none;endFill=1;" target="switch_a" value="">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>
        <mxCell id="switch_a" parent="1" style="shape=mxgraph.cisco.switches.workgroup_switch;html=1;pointerEvents=1;dashed=0;fillColor=#d5e8d4;strokeColor=#82b366;strokeWidth=2;verticalLabelPosition=bottom;verticalAlign=top;align=center;outlineConnect=0;fontSize=11;" value="" vertex="1">
          <mxGeometry height="60" width="80" x="165" y="785" as="geometry" />
        </mxCell>
        <mxCell id="e_swa_pca1" edge="1" parent="1" source="switch_a" style="edgeStyle=orthogonalEdgeStyle;html=1;exitX=0;exitY=0.5;exitDx=0;exitDy=0;entryX=0.5;entryY=0;entryDx=0;entryDy=0;strokeColor=#666666;strokeWidth=1.5;endArrow=block;startArrow=none;endFill=1;" target="pc_a1" value="">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>
        <mxCell id="pc_a1" parent="1" style="shape=mxgraph.cisco.computers_and_peripherals.pc;html=1;pointerEvents=1;dashed=0;fillColor=#f5f5f5;strokeColor=#666666;strokeWidth=1.5;verticalLabelPosition=bottom;verticalAlign=top;align=center;outlineConnect=0;fontSize=10;" value="PC-A1&#xa;192.168.1.10/24&#xa;VLAN 10 Admin" vertex="1">
          <mxGeometry height="50" width="60" x="80" y="940" as="geometry" />
        </mxCell>
        <mxCell id="e_swa_pca2" edge="1" parent="1" source="switch_a" style="edgeStyle=orthogonalEdgeStyle;html=1;exitX=0.5;exitY=1;exitDx=0;exitDy=0;entryX=0.5;entryY=0;entryDx=0;entryDy=0;strokeColor=#666666;strokeWidth=1.5;endArrow=block;startArrow=none;endFill=1;" target="pc_a2" value="">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>
        <mxCell id="pc_a2" parent="1" style="shape=mxgraph.cisco.computers_and_peripherals.pc;html=1;pointerEvents=1;dashed=0;fillColor=#f5f5f5;strokeColor=#666666;strokeWidth=1.5;verticalLabelPosition=bottom;verticalAlign=top;align=center;outlineConnect=0;fontSize=10;" value="PC-A2&#xa;192.168.1.11/24&#xa;VLAN 10 Admin" vertex="1">
          <mxGeometry height="50" width="60" x="175" y="940" as="geometry" />
        </mxCell>
        <mxCell id="e_swa_pca3" edge="1" parent="1" source="switch_a" style="edgeStyle=orthogonalEdgeStyle;html=1;exitX=1;exitY=0.5;exitDx=0;exitDy=0;entryX=0.5;entryY=0;entryDx=0;entryDy=0;strokeColor=#666666;strokeWidth=1.5;endArrow=block;startArrow=none;endFill=1;" target="pc_a3" value="">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>
        <mxCell id="pc_a3" parent="1" style="shape=mxgraph.cisco.computers_and_peripherals.pc;html=1;pointerEvents=1;dashed=0;fillColor=#dae8fc;strokeColor=#6c8ebf;strokeWidth=1.5;verticalLabelPosition=bottom;verticalAlign=top;align=center;outlineConnect=0;fontSize=10;" value="PC-A3&#xa;192.168.1.12/24&#xa;VLAN 20 Clinical" vertex="1">
          <mxGeometry height="50" width="60" x="270" y="940" as="geometry" />
        </mxCell>
        <mxCell id="campus_b_box" parent="1" style="rounded=1;whiteSpace=wrap;html=1;fillColor=none;strokeColor=#6c8ebf;strokeWidth=2;dashed=1;dashPattern=8 4;verticalAlign=top;fontSize=13;fontStyle=1;fontColor=#1e3a5f;arcSize=3;" value="Hospital B - Mernda Campus" vertex="1">
          <mxGeometry height="600" width="330" x="535" y="560" as="geometry" />
        </mxCell>
        <mxCell id="router_b" parent="1" style="shape=mxgraph.cisco.routers.router;html=1;pointerEvents=1;dashed=0;fillColor=#dae8fc;strokeColor=#6c8ebf;strokeWidth=2;verticalLabelPosition=bottom;verticalAlign=top;align=center;outlineConnect=0;fontSize=11;" value="" vertex="1">
          <mxGeometry height="70" width="80" x="660" y="590" as="geometry" />
        </mxCell>
        <mxCell id="e_rb_swb" edge="1" parent="1" source="router_b" style="edgeStyle=orthogonalEdgeStyle;html=1;exitX=0.5;exitY=1;exitDx=0;exitDy=0;entryX=0.5;entryY=0;entryDx=0;entryDy=0;strokeColor=#82b366;strokeWidth=2;endArrow=block;startArrow=none;endFill=1;" target="switch_b" value="">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>
        <mxCell id="switch_b" parent="1" style="shape=mxgraph.cisco.switches.workgroup_switch;html=1;pointerEvents=1;dashed=0;fillColor=#d5e8d4;strokeColor=#82b366;strokeWidth=2;verticalLabelPosition=bottom;verticalAlign=top;align=center;outlineConnect=0;fontSize=11;" value="" vertex="1">
          <mxGeometry height="60" width="80" x="660" y="790" as="geometry" />
        </mxCell>
        <mxCell id="e_swb_pcb1" edge="1" parent="1" source="switch_b" style="edgeStyle=orthogonalEdgeStyle;html=1;exitX=0;exitY=0.5;exitDx=0;exitDy=0;entryX=0.5;entryY=0;entryDx=0;entryDy=0;strokeColor=#666666;strokeWidth=1.5;endArrow=block;startArrow=none;endFill=1;" target="pc_b1" value="">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>
        <mxCell id="pc_b1" parent="1" style="shape=mxgraph.cisco.computers_and_peripherals.pc;html=1;pointerEvents=1;dashed=0;fillColor=#f5f5f5;strokeColor=#666666;strokeWidth=1.5;verticalLabelPosition=bottom;verticalAlign=top;align=center;outlineConnect=0;fontSize=10;" value="PC-B1&#xa;192.168.2.10/24&#xa;VLAN 10 Admin" vertex="1">
          <mxGeometry height="50" width="60" x="555" y="940" as="geometry" />
        </mxCell>
        <mxCell id="e_swb_pcb2" edge="1" parent="1" source="switch_b" style="edgeStyle=orthogonalEdgeStyle;html=1;exitX=0.5;exitY=1;exitDx=0;exitDy=0;entryX=0.5;entryY=0;entryDx=0;entryDy=0;strokeColor=#666666;strokeWidth=1.5;endArrow=block;startArrow=none;endFill=1;" target="pc_b2" value="">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>
        <mxCell id="pc_b2" parent="1" style="shape=mxgraph.cisco.computers_and_peripherals.pc;html=1;pointerEvents=1;dashed=0;fillColor=#f5f5f5;strokeColor=#666666;strokeWidth=1.5;verticalLabelPosition=bottom;verticalAlign=top;align=center;outlineConnect=0;fontSize=10;" value="PC-B2&#xa;192.168.2.11/24&#xa;VLAN 10 Admin" vertex="1">
          <mxGeometry height="50" width="60" x="665" y="940" as="geometry" />
        </mxCell>
        <mxCell id="e_swb_pcb3" edge="1" parent="1" source="switch_b" style="edgeStyle=orthogonalEdgeStyle;html=1;exitX=1;exitY=0.5;exitDx=0;exitDy=0;entryX=0.5;entryY=0;entryDx=0;entryDy=0;strokeColor=#666666;strokeWidth=1.5;endArrow=none;startArrow=none;endFill=0;" target="pc_b3" value="">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>
        <mxCell id="pc_b3" parent="1" style="shape=mxgraph.cisco.computers_and_peripherals.pc;html=1;pointerEvents=1;dashed=0;fillColor=#dae8fc;strokeColor=#6c8ebf;strokeWidth=1.5;verticalLabelPosition=bottom;verticalAlign=top;align=center;outlineConnect=0;fontSize=10;" value="PC-B3&#xa;192.168.2.12/24&#xa;VLAN 20 Clinical" vertex="1">
          <mxGeometry height="50" width="60" x="775" y="940" as="geometry" />
        </mxCell>
        <mxCell id="campus_c_box" parent="1" style="rounded=1;whiteSpace=wrap;html=1;fillColor=none;strokeColor=#6c8ebf;strokeWidth=2;dashed=1;dashPattern=8 4;verticalAlign=top;fontSize=13;fontStyle=1;fontColor=#1e3a5f;arcSize=3;" value="Hospital C - CBD Campus" vertex="1">
          <mxGeometry height="600" width="330" x="1010" y="560" as="geometry" />
        </mxCell>
        <mxCell id="router_c" parent="1" style="shape=mxgraph.cisco.routers.router;html=1;pointerEvents=1;dashed=0;fillColor=#dae8fc;strokeColor=#6c8ebf;strokeWidth=2;verticalLabelPosition=bottom;verticalAlign=top;align=center;outlineConnect=0;fontSize=11;" value="" vertex="1">
          <mxGeometry height="70" width="80" x="1135" y="590" as="geometry" />
        </mxCell>
        <mxCell id="e_rc_swc" edge="1" parent="1" source="router_c" style="edgeStyle=orthogonalEdgeStyle;html=1;exitX=0.5;exitY=1;exitDx=0;exitDy=0;entryX=0.5;entryY=0;entryDx=0;entryDy=0;strokeColor=#82b366;strokeWidth=2;endArrow=block;startArrow=none;endFill=1;" target="switch_c" value="">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>
        <mxCell id="switch_c" parent="1" style="shape=mxgraph.cisco.switches.workgroup_switch;html=1;pointerEvents=1;dashed=0;fillColor=#d5e8d4;strokeColor=#82b366;strokeWidth=2;verticalLabelPosition=bottom;verticalAlign=top;align=center;outlineConnect=0;fontSize=11;" value="" vertex="1">
          <mxGeometry height="60" width="80" x="1135" y="790" as="geometry" />
        </mxCell>
        <mxCell id="e_swc_pcc1" edge="1" parent="1" source="switch_c" style="html=1;exitX=0;exitY=0.5;exitDx=0;exitDy=0;entryX=0.5;entryY=0;entryDx=0;entryDy=0;strokeColor=#666666;strokeWidth=1.5;endArrow=block;startArrow=none;endFill=1;edgeStyle=orthogonalEdgeStyle;" target="pc_c1" value="">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>
        <mxCell id="pc_c1" parent="1" style="shape=mxgraph.cisco.computers_and_peripherals.pc;html=1;pointerEvents=1;dashed=0;fillColor=#f5f5f5;strokeColor=#666666;strokeWidth=1.5;verticalLabelPosition=bottom;verticalAlign=top;align=center;outlineConnect=0;fontSize=10;" value="PC-C1&#xa;192.168.3.10/24&#xa;VLAN 10 Admin" vertex="1">
          <mxGeometry height="50" width="60" x="1030" y="940" as="geometry" />
        </mxCell>
        <mxCell id="e_swc_pcc2" edge="1" parent="1" source="switch_c" style="edgeStyle=orthogonalEdgeStyle;html=1;exitX=0.5;exitY=1;exitDx=0;exitDy=0;entryX=0.5;entryY=0;entryDx=0;entryDy=0;strokeColor=#666666;strokeWidth=1.5;endArrow=block;startArrow=none;endFill=1;" target="pc_c2" value="">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>
        <mxCell id="pc_c2" parent="1" style="shape=mxgraph.cisco.computers_and_peripherals.pc;html=1;pointerEvents=1;dashed=0;fillColor=#f5f5f5;strokeColor=#666666;strokeWidth=1.5;verticalLabelPosition=bottom;verticalAlign=top;align=center;outlineConnect=0;fontSize=10;" value="PC-C2&#xa;192.168.3.11/24&#xa;VLAN 10 Admin" vertex="1">
          <mxGeometry height="50" width="60" x="1140" y="940" as="geometry" />
        </mxCell>
        <mxCell id="e_swc_pcc3" edge="1" parent="1" source="switch_c" style="edgeStyle=orthogonalEdgeStyle;html=1;exitX=1;exitY=0.5;exitDx=0;exitDy=0;entryX=0.5;entryY=0;entryDx=0;entryDy=0;strokeColor=#666666;strokeWidth=1.5;endArrow=block;startArrow=none;endFill=1;" target="pc_c3" value="">
          <mxGeometry relative="1" as="geometry" />
        </mxCell>
        <mxCell id="pc_c3" parent="1" style="shape=mxgraph.cisco.computers_and_peripherals.pc;html=1;pointerEvents=1;dashed=0;fillColor=#dae8fc;strokeColor=#6c8ebf;strokeWidth=1.5;verticalLabelPosition=bottom;verticalAlign=top;align=center;outlineConnect=0;fontSize=10;" value="PC-C3&#xa;192.168.3.12/24&#xa;VLAN 20 Clinical" vertex="1">
          <mxGeometry height="50" width="60" x="1250" y="940" as="geometry" />
        </mxCell>
        <mxCell id="flow_box" parent="1" style="rounded=1;whiteSpace=wrap;html=1;fillColor=#fff9db;strokeColor=#d79b00;strokeWidth=1.5;" value="" vertex="1">
          <mxGeometry height="220" width="560" x="60" y="1630" as="geometry" />
        </mxCell>
        <mxCell id="flow_title" parent="1" style="text;html=1;strokeColor=none;fillColor=none;align=left;verticalAlign=middle;whiteSpace=wrap;rounded=0;fontSize=13;fontStyle=1;fontColor=#b46504;" value="Traffic Flow — How it works" vertex="1">
          <mxGeometry height="20" width="300" x="80" y="1644" as="geometry" />
        </mxCell>
        <mxCell id="flow_1" parent="1" style="text;html=1;strokeColor=none;fillColor=none;align=left;verticalAlign=middle;whiteSpace=wrap;rounded=0;fontSize=11;fontColor=#333333;" value="Campus → Central Server:   PC → Switch → Router → Firewall → Central Server" vertex="1">
          <mxGeometry height="20" width="520" x="80" y="1672" as="geometry" />
        </mxCell>
        <mxCell id="flow_2" parent="1" style="text;html=1;strokeColor=none;fillColor=none;align=left;verticalAlign=middle;whiteSpace=wrap;rounded=0;fontSize=11;fontColor=#333333;" value="Campus → Internet:              PC → Switch → Router → Firewall → ISP Router → Internet" vertex="1">
          <mxGeometry height="20" width="520" x="80" y="1698" as="geometry" />
        </mxCell>
        <mxCell id="flow_3" parent="1" style="text;html=1;strokeColor=none;fillColor=none;align=left;verticalAlign=middle;whiteSpace=wrap;rounded=0;fontSize=11;fontColor=#333333;" value="Campus A → Campus B:     Router A → (VPN tunnel) → Router B → Switch B → PC" vertex="1">
          <mxGeometry height="20" width="520" x="80" y="1724" as="geometry" />
        </mxCell>
        <mxCell id="flow_4" parent="1" style="text;html=1;strokeColor=none;fillColor=none;align=left;verticalAlign=middle;whiteSpace=wrap;rounded=0;fontSize=11;fontColor=#b85450;fontStyle=1;" value="ISP Router has NO knowledge of internal network — it only sees the firewall&#39;s public IP" vertex="1">
          <mxGeometry height="20" width="520" x="80" y="1754" as="geometry" />
        </mxCell>
        <mxCell id="flow_5" parent="1" style="text;html=1;strokeColor=none;fillColor=none;align=left;verticalAlign=middle;whiteSpace=wrap;rounded=0;fontSize=11;fontColor=#333333;" value="Campus → Campus Server:  PC → Switch → Router — local only, never leaves campus LAN" vertex="1">
          <mxGeometry height="20" width="520" x="80" y="1780" as="geometry" />
        </mxCell>
        <mxCell id="flow_6" parent="1" style="text;html=1;strokeColor=none;fillColor=none;align=left;verticalAlign=middle;whiteSpace=wrap;rounded=0;fontSize=11;fontColor=#b85450;fontStyle=1;" value="Single firewall = one choke point — every packet in/out is inspected here" vertex="1">
          <mxGeometry height="20" width="520" x="80" y="1806" as="geometry" />
        </mxCell>
        <mxCell id="legend_box" parent="1" style="rounded=1;whiteSpace=wrap;html=1;fillColor=#f9f9f9;strokeColor=#666666;strokeWidth=1;" value="" vertex="1">
          <mxGeometry height="220" width="680" x="660" y="1630" as="geometry" />
        </mxCell>
        <mxCell id="legend_title" parent="1" style="text;html=1;strokeColor=none;fillColor=none;align=left;verticalAlign=middle;whiteSpace=wrap;rounded=0;fontSize=13;fontStyle=1;" value="Legend" vertex="1">
          <mxGeometry height="20" width="100" x="680" y="1644" as="geometry" />
        </mxCell>
        <mxCell id="leg_wan" edge="1" parent="1" style="edgeStyle=none;html=1;strokeColor=#b85450;strokeWidth=2;endArrow=block;startArrow=block;endFill=1;startFill=0;" value="">
          <mxGeometry as="geometry">
            <mxPoint x="680" y="1678" as="sourcePoint" />
            <mxPoint x="730" y="1678" as="targetPoint" />
          </mxGeometry>
        </mxCell>
        <mxCell id="leg_wan_lbl" parent="1" style="text;html=1;strokeColor=none;fillColor=none;align=left;verticalAlign=middle;fontSize=11;" value="Firewall-protected WAN link" vertex="1">
          <mxGeometry height="20" width="220" x="738" y="1668" as="geometry" />
        </mxCell>
        <mxCell id="leg_lan" edge="1" parent="1" style="edgeStyle=none;html=1;strokeColor=#82b366;strokeWidth=2;endArrow=block;startArrow=none;endFill=1;" value="">
          <mxGeometry as="geometry">
            <mxPoint x="680" y="1704" as="sourcePoint" />
            <mxPoint x="730" y="1704" as="targetPoint" />
          </mxGeometry>
        </mxCell>
        <mxCell id="leg_lan_lbl" parent="1" style="text;html=1;strokeColor=none;fillColor=none;align=left;verticalAlign=middle;fontSize=11;" value="LAN link (Router → Switch)" vertex="1">
          <mxGeometry height="20" width="220" x="738" y="1694" as="geometry" />
        </mxCell>
        <mxCell id="leg_eth" edge="1" parent="1" style="edgeStyle=none;html=1;strokeColor=#666666;strokeWidth=1.5;endArrow=block;startArrow=none;endFill=1;" value="">
          <mxGeometry as="geometry">
            <mxPoint x="680" y="1730" as="sourcePoint" />
            <mxPoint x="730" y="1730" as="targetPoint" />
          </mxGeometry>
        </mxCell>
        <mxCell id="leg_eth_lbl" parent="1" style="text;html=1;strokeColor=none;fillColor=none;align=left;verticalAlign=middle;fontSize=11;" value="Ethernet (Switch → End device)" vertex="1">
          <mxGeometry height="20" width="220" x="738" y="1720" as="geometry" />
        </mxCell>
        <mxCell id="leg_vpn" edge="1" parent="1" style="edgeStyle=none;html=1;strokeColor=#d79b00;strokeWidth=3;dashed=1;dashPattern=10 5;endArrow=block;startArrow=block;endFill=1;startFill=1;" value="">
          <mxGeometry as="geometry">
            <mxPoint x="680" y="1756" as="sourcePoint" />
            <mxPoint x="730" y="1756" as="targetPoint" />
          </mxGeometry>
        </mxCell>
        <mxCell id="leg_vpn_lbl" parent="1" style="text;html=1;strokeColor=none;fillColor=none;align=left;verticalAlign=middle;fontSize=11;" value="IPSec VPN tunnel (AES-256 encrypted)" vertex="1">
          <mxGeometry height="20" width="260" x="738" y="1746" as="geometry" />
        </mxCell>
        <mxCell id="leg_fw_box" parent="1" style="rounded=1;fillColor=#f8cecc;strokeColor=#b85450;strokeWidth=1;" value="" vertex="1">
          <mxGeometry height="12" width="16" x="980" y="1668" as="geometry" />
        </mxCell>
        <mxCell id="leg_fw_lbl" parent="1" style="text;html=1;strokeColor=none;fillColor=none;align=left;verticalAlign=middle;fontSize=11;" value="Firewall (single central choke point)" vertex="1">
          <mxGeometry height="20" width="280" x="1002" y="1662" as="geometry" />
        </mxCell>
        <mxCell id="leg_rtr_box" parent="1" style="rounded=1;fillColor=#dae8fc;strokeColor=#6c8ebf;strokeWidth=1;" value="" vertex="1">
          <mxGeometry height="12" width="16" x="980" y="1694" as="geometry" />
        </mxCell>
        <mxCell id="leg_rtr_lbl" parent="1" style="text;html=1;strokeColor=none;fillColor=none;align=left;verticalAlign=middle;fontSize=11;" value="Router (campus gateway + VPN)" vertex="1">
          <mxGeometry height="20" width="280" x="1002" y="1688" as="geometry" />
        </mxCell>
        <mxCell id="leg_sw_box" parent="1" style="rounded=1;fillColor=#d5e8d4;strokeColor=#82b366;strokeWidth=1;" value="" vertex="1">
          <mxGeometry height="12" width="16" x="980" y="1720" as="geometry" />
        </mxCell>
        <mxCell id="leg_sw_lbl" parent="1" style="text;html=1;strokeColor=none;fillColor=none;align=left;verticalAlign=middle;fontSize=11;" value="Switch (VLAN 10 Admin / VLAN 20 Clinical)" vertex="1">
          <mxGeometry height="20" width="280" x="1002" y="1714" as="geometry" />
        </mxCell>
        <mxCell id="leg_srv_box" parent="1" style="rounded=1;fillColor=#e1d5e7;strokeColor=#9673a6;strokeWidth=1;" value="" vertex="1">
          <mxGeometry height="12" width="16" x="980" y="1746" as="geometry" />
        </mxCell>
        <mxCell id="leg_srv_lbl" parent="1" style="text;html=1;strokeColor=none;fillColor=none;align=left;verticalAlign=middle;fontSize=11;" value="Server (purple = central storage, grey = local)" vertex="1">
          <mxGeometry height="20" width="300" x="1002" y="1740" as="geometry" />
        </mxCell>
        <mxCell id="leg_admin_box" parent="1" style="rounded=1;fillColor=#f5f5f5;strokeColor=#666666;strokeWidth=1;" value="" vertex="1">
          <mxGeometry height="12" width="16" x="980" y="1772" as="geometry" />
        </mxCell>
        <mxCell id="leg_admin_lbl" parent="1" style="text;html=1;strokeColor=none;fillColor=none;align=left;verticalAlign=middle;fontSize=11;" value="PC — grey = Admin (VLAN 10)" vertex="1">
          <mxGeometry height="20" width="260" x="1002" y="1766" as="geometry" />
        </mxCell>
        <mxCell id="leg_clin_box" parent="1" style="rounded=1;fillColor=#dae8fc;strokeColor=#6c8ebf;strokeWidth=1;" value="" vertex="1">
          <mxGeometry height="12" width="16" x="980" y="1798" as="geometry" />
        </mxCell>
        <mxCell id="leg_clin_lbl" parent="1" style="text;html=1;strokeColor=none;fillColor=none;align=left;verticalAlign=middle;fontSize=11;" value="PC — blue = Clinical (VLAN 20)" vertex="1">
          <mxGeometry height="20" width="260" x="1002" y="1792" as="geometry" />
        </mxCell>
        <mxCell id="subnet_table" parent="1" style="text;html=1;strokeColor=#6c8ebf;fillColor=#dae8fc;align=left;verticalAlign=top;whiteSpace=wrap;rounded=1;fontSize=11;spacingLeft=10;spacingTop=6;" value="&lt;b&gt;IP Address Reference&lt;/b&gt;&lt;br&gt;&lt;br&gt;WAN Links (ISP ↔ Routers): 10.0.0.0/30, 10.0.1.0/30, 10.0.2.0/30&lt;br&gt;Central Server (Patient Data): 172.16.0.10/24&lt;br&gt;Hospital A LAN: 192.168.1.0/24 — GW 192.168.1.1&lt;br&gt;Hospital B LAN: 192.168.2.0/24 — GW 192.168.2.1&lt;br&gt;Hospital C LAN: 192.168.3.0/24 — GW 192.168.3.1" vertex="1">
          <mxGeometry height="110" width="560" x="60" y="1870" as="geometry" />
        </mxCell>
        <mxCell id="OJkc2mzw6svLMNVJvNq--8" parent="1" style="text;html=1;whiteSpace=wrap;strokeColor=none;fillColor=none;align=center;verticalAlign=middle;rounded=0;" value="&lt;font style=&quot;color: light-dark(rgb(0, 0, 0), rgb(255, 180, 0));&quot;&gt;(VPN TUNNEL)&lt;/font&gt;" vertex="1">
          <mxGeometry height="30" width="290" x="490" y="440" as="geometry" />
        </mxCell>
        <mxCell id="OJkc2mzw6svLMNVJvNq--9" parent="1" style="image;html=1;image=img/lib/clip_art/computers/Server_128x128.png" value="Shared Server&lt;div&gt;(Authentication · Caching · File Services)&lt;/div&gt;" vertex="1">
          <mxGeometry height="80" width="80" x="235" y="155" as="geometry" />
        </mxCell>
        <mxCell id="OJkc2mzw6svLMNVJvNq--12" parent="1" style="text;html=1;whiteSpace=wrap;strokeColor=none;fillColor=none;align=center;verticalAlign=middle;rounded=0;" value="&lt;span style=&quot;font-size: 11px; white-space: nowrap;&quot;&gt;Router C&lt;/span&gt;&lt;br style=&quot;font-size: 11px; white-space: nowrap;&quot;&gt;&lt;span style=&quot;font-size: 11px; white-space: nowrap;&quot;&gt;Cisco 2511&lt;/span&gt;&lt;br style=&quot;font-size: 11px; white-space: nowrap;&quot;&gt;&lt;br style=&quot;font-size: 11px; white-space: nowrap;&quot;&gt;&lt;span style=&quot;font-size: 11px; white-space: nowrap;&quot;&gt;WAN: 10.0.2.2/30&lt;/span&gt;&lt;br style=&quot;font-size: 11px; white-space: nowrap;&quot;&gt;&lt;span style=&quot;font-size: 11px; white-space: nowrap;&quot;&gt;LAN: 192.168.3.1/24&lt;/span&gt;&lt;br style=&quot;font-size: 11px; white-space: nowrap;&quot;&gt;&lt;br style=&quot;font-size: 11px; white-space: nowrap;&quot;&gt;&lt;span style=&quot;font-size: 11px; white-space: nowrap;&quot;&gt;IPSec VPN on WAN&lt;/span&gt;" vertex="1">
          <mxGeometry height="30" width="60" x="1070" y="660" as="geometry" />
        </mxCell>
        <mxCell id="OJkc2mzw6svLMNVJvNq--13" parent="1" style="text;html=1;whiteSpace=wrap;strokeColor=none;fillColor=none;align=center;verticalAlign=middle;rounded=0;" value="&lt;span style=&quot;font-size: 11px; white-space: nowrap;&quot;&gt;Router B&lt;/span&gt;&lt;br style=&quot;font-size: 11px; white-space: nowrap;&quot;&gt;&lt;span style=&quot;font-size: 11px; white-space: nowrap;&quot;&gt;Cisco 2511&lt;/span&gt;&lt;br style=&quot;font-size: 11px; white-space: nowrap;&quot;&gt;&lt;br style=&quot;font-size: 11px; white-space: nowrap;&quot;&gt;&lt;span style=&quot;font-size: 11px; white-space: nowrap;&quot;&gt;WAN: 10.0.1.2/30&lt;/span&gt;&lt;br style=&quot;font-size: 11px; white-space: nowrap;&quot;&gt;&lt;span style=&quot;font-size: 11px; white-space: nowrap;&quot;&gt;LAN: 192.168.2.1/24&lt;/span&gt;&lt;br style=&quot;font-size: 11px; white-space: nowrap;&quot;&gt;&lt;br style=&quot;font-size: 11px; white-space: nowrap;&quot;&gt;&lt;span style=&quot;font-size: 11px; white-space: nowrap;&quot;&gt;IPSec VPN on WAN&lt;/span&gt;" vertex="1">
          <mxGeometry height="30" width="60" x="592" y="650" as="geometry" />
        </mxCell>
        <mxCell id="OJkc2mzw6svLMNVJvNq--15" parent="1" style="text;html=1;whiteSpace=wrap;strokeColor=none;fillColor=none;align=center;verticalAlign=middle;rounded=0;" value="&lt;span style=&quot;font-size: 11px; white-space: nowrap;&quot;&gt;Router A&lt;/span&gt;&lt;br style=&quot;font-size: 11px; white-space: nowrap;&quot;&gt;&lt;span style=&quot;font-size: 11px; white-space: nowrap;&quot;&gt;Cisco 2511&lt;/span&gt;&lt;br style=&quot;font-size: 11px; white-space: nowrap;&quot;&gt;&lt;br style=&quot;font-size: 11px; white-space: nowrap;&quot;&gt;&lt;span style=&quot;font-size: 11px; white-space: nowrap;&quot;&gt;WAN: 10.0.0.2/30&lt;/span&gt;&lt;br style=&quot;font-size: 11px; white-space: nowrap;&quot;&gt;&lt;span style=&quot;font-size: 11px; white-space: nowrap;&quot;&gt;LAN: 192.168.1.1/24&lt;/span&gt;&lt;br style=&quot;font-size: 11px; white-space: nowrap;&quot;&gt;&lt;br style=&quot;font-size: 11px; white-space: nowrap;&quot;&gt;&lt;span style=&quot;font-size: 11px; white-space: nowrap;&quot;&gt;IPSec VPN on WAN&lt;/span&gt;" vertex="1">
          <mxGeometry height="30" width="60" x="90" y="650" as="geometry" />
        </mxCell>
        <mxCell id="OJkc2mzw6svLMNVJvNq--16" parent="1" style="text;html=1;whiteSpace=wrap;strokeColor=none;fillColor=none;align=center;verticalAlign=middle;rounded=0;" value="&lt;span style=&quot;font-size: 11px; white-space: nowrap;&quot;&gt;Switch B&lt;/span&gt;&lt;br style=&quot;font-size: 11px; white-space: nowrap;&quot;&gt;&lt;span style=&quot;font-size: 11px; white-space: nowrap;&quot;&gt;Cisco 2960&lt;/span&gt;&lt;br style=&quot;font-size: 11px; white-space: nowrap;&quot;&gt;&lt;br style=&quot;font-size: 11px; white-space: nowrap;&quot;&gt;&lt;span style=&quot;font-size: 11px; white-space: nowrap;&quot;&gt;VLAN 10 — Admin&lt;/span&gt;&lt;br style=&quot;font-size: 11px; white-space: nowrap;&quot;&gt;&lt;span style=&quot;font-size: 11px; white-space: nowrap;&quot;&gt;VLAN 20 — Clinical&lt;/span&gt;" vertex="1">
          <mxGeometry height="30" width="60" x="605" y="850" as="geometry" />
        </mxCell>
        <mxCell id="OJkc2mzw6svLMNVJvNq--17" parent="1" style="text;html=1;whiteSpace=wrap;strokeColor=none;fillColor=none;align=center;verticalAlign=middle;rounded=0;" value="&lt;span style=&quot;font-size: 11px; white-space: nowrap;&quot;&gt;Switch A&lt;/span&gt;&lt;br style=&quot;font-size: 11px; white-space: nowrap;&quot;&gt;&lt;span style=&quot;font-size: 11px; white-space: nowrap;&quot;&gt;Cisco 2960&lt;/span&gt;&lt;br style=&quot;font-size: 11px; white-space: nowrap;&quot;&gt;&lt;br style=&quot;font-size: 11px; white-space: nowrap;&quot;&gt;&lt;span style=&quot;font-size: 11px; white-space: nowrap;&quot;&gt;VLAN 10 — Admin&lt;/span&gt;&lt;br style=&quot;font-size: 11px; white-space: nowrap;&quot;&gt;&lt;span style=&quot;font-size: 11px; white-space: nowrap;&quot;&gt;VLAN 20 — Clinical&lt;/span&gt;&lt;div&gt;&lt;span style=&quot;font-size: 11px; white-space: nowrap;&quot;&gt;&lt;br&gt;&lt;/span&gt;&lt;/div&gt;" vertex="1">
          <mxGeometry height="30" width="60" x="235" y="860" as="geometry" />
        </mxCell>
        <mxCell id="OJkc2mzw6svLMNVJvNq--18" parent="1" style="text;html=1;whiteSpace=wrap;strokeColor=none;fillColor=none;align=center;verticalAlign=middle;rounded=0;" value="&lt;span style=&quot;font-size: 11px; white-space: nowrap;&quot;&gt;Switch C&lt;/span&gt;&lt;br style=&quot;font-size: 11px; white-space: nowrap;&quot;&gt;&lt;span style=&quot;font-size: 11px; white-space: nowrap;&quot;&gt;Cisco 2960&lt;/span&gt;&lt;br style=&quot;font-size: 11px; white-space: nowrap;&quot;&gt;&lt;br style=&quot;font-size: 11px; white-space: nowrap;&quot;&gt;&lt;span style=&quot;font-size: 11px; white-space: nowrap;&quot;&gt;VLAN 10 — Admin&lt;/span&gt;&lt;br style=&quot;font-size: 11px; white-space: nowrap;&quot;&gt;&lt;span style=&quot;font-size: 11px; white-space: nowrap;&quot;&gt;VLAN 20 — Clinical&lt;/span&gt;" vertex="1">
          <mxGeometry height="30" width="60" x="1080" y="850" as="geometry" />
        </mxCell>
        <mxCell id="OJkc2mzw6svLMNVJvNq--19" parent="1" style="text;html=1;whiteSpace=wrap;strokeColor=none;fillColor=none;align=center;verticalAlign=middle;rounded=0;" value="&lt;span style=&quot;font-size: 11px; font-weight: 700; white-space: nowrap;&quot;&gt;Central Firewall&lt;/span&gt;&lt;br style=&quot;font-size: 11px; font-weight: 700; white-space: nowrap;&quot;&gt;&lt;br style=&quot;font-size: 11px; font-weight: 700; white-space: nowrap;&quot;&gt;&lt;span style=&quot;font-size: 11px; font-weight: 700; white-space: nowrap;&quot;&gt;Cisco ASA&lt;/span&gt;&lt;br style=&quot;font-size: 11px; font-weight: 700; white-space: nowrap;&quot;&gt;&lt;span style=&quot;font-size: 11px; font-weight: 700; white-space: nowrap;&quot;&gt;ACL - Stateful Inspection - NAT&lt;/span&gt;&lt;br style=&quot;font-size: 11px; font-weight: 700; white-space: nowrap;&quot;&gt;&lt;br style=&quot;font-size: 11px; font-weight: 700; white-space: nowrap;&quot;&gt;&lt;span style=&quot;font-size: 11px; font-weight: 700; white-space: nowrap;&quot;&gt;ALL traffic passes through here&lt;/span&gt;" vertex="1">
          <mxGeometry height="30" width="60" x="460" y="240" as="geometry" />
        </mxCell>
        <mxCell id="OJkc2mzw6svLMNVJvNq--20" parent="1" style="text;html=1;whiteSpace=wrap;strokeColor=none;fillColor=none;align=center;verticalAlign=middle;rounded=0;" value="&lt;span style=&quot;font-size: 11px; white-space: nowrap;&quot;&gt;ISP Router&lt;/span&gt;&lt;br style=&quot;font-size: 11px; white-space: nowrap;&quot;&gt;&lt;br style=&quot;font-size: 11px; white-space: nowrap;&quot;&gt;&lt;span style=&quot;font-size: 11px; white-space: nowrap;&quot;&gt;fa0/0: 10.0.0.1/30&lt;/span&gt;&lt;br style=&quot;font-size: 11px; white-space: nowrap;&quot;&gt;&lt;span style=&quot;font-size: 11px; white-space: nowrap;&quot;&gt;fa0/1: 10.0.1.1/30&lt;/span&gt;&lt;br style=&quot;font-size: 11px; white-space: nowrap;&quot;&gt;&lt;span style=&quot;font-size: 11px; white-space: nowrap;&quot;&gt;fa0/2: 10.0.2.1/30&lt;/span&gt;" vertex="1">
          <mxGeometry height="30" width="60" x="470" y="30" as="geometry" />
        </mxCell>
        <mxCell id="OJkc2mzw6svLMNVJvNq--21" parent="1" style="ellipse;shape=cloud;whiteSpace=wrap;html=1;" value="Internet&lt;div&gt;(Public network)&lt;/div&gt;" vertex="1">
          <mxGeometry height="118" width="165" x="523" y="-160" as="geometry" />
        </mxCell>
        <mxCell id="OJkc2mzw6svLMNVJvNq--22" parent="1" style="image;html=1;image=img/lib/clip_art/networking/Firewall-page1_128x128.png" value="" vertex="1">
          <mxGeometry height="80" width="80" x="565.5" y="154" as="geometry" />
        </mxCell>
        <mxCell id="OJkc2mzw6svLMNVJvNq--23" parent="1" style="image;aspect=fixed;perimeter=ellipsePerimeter;html=1;align=center;shadow=0;dashed=0;spacingTop=3;image=img/lib/active_directory/database_server.svg;" value="&lt;div&gt;&lt;span style=&quot;font-size: 11px; background-color: rgb(211, 213, 214);&quot;&gt;Central Server&lt;/span&gt;&lt;/div&gt;&lt;div&gt;&lt;span style=&quot;font-size: 11px; background-color: rgb(211, 213, 214);&quot;&gt;(Patient Data Storage)&lt;/span&gt;&lt;/div&gt;&lt;div&gt;&lt;span style=&quot;font-size: 11px; background-color: rgb(211, 213, 214);&quot;&gt;&lt;br&gt;&lt;/span&gt;&lt;/div&gt;&lt;div&gt;&lt;span style=&quot;font-size: 11px; background-color: rgb(211, 213, 214);&quot;&gt;172.16.0.10/24&lt;/span&gt;&lt;/div&gt;&lt;div&gt;&lt;span style=&quot;font-size: 11px; background-color: rgb(211, 213, 214);&quot;&gt;&lt;br&gt;&lt;/span&gt;&lt;/div&gt;&lt;div&gt;&lt;span style=&quot;font-size: 11px; background-color: rgb(211, 213, 214);&quot;&gt;All campus patient&lt;/span&gt;&lt;/div&gt;&lt;div&gt;&lt;span style=&quot;font-size: 11px; background-color: rgb(211, 213, 214);&quot;&gt;records stored here&lt;/span&gt;&lt;/div&gt;" vertex="1">
          <mxGeometry height="81" width="66.42" x="835" y="154" as="geometry" />
        </mxCell>
      </root>
    </mxGraphModel>
  </diagram>
</mxfile>


Now what do the devices do in here:

- Internet (Public Network)
The outside world the road that all traffic between campuses and external services travels on.

- ISP Router
Your network's front door to the internet forwards traffic in and out but has zero knowledge of what's inside your network.

- Central Firewall (Cisco ASA)
The single gatekeeper every packet in the entire network passes through here and gets inspected, allowed, or blocked.

- Central Server / Patient Data Storage (Database Server)
Stores all patient records for all three campuses the single source of truth for the entire organisation.

- Shared Campus Server
Handles authentication, file services and caching for all three campuses keeps the network running even if the patient data server has issues.

- Router A / B / C (Cisco 2511)
Each campus's gateway connects the campus LAN to the firewall and runs the IPSec VPN tunnel to encrypt inter-campus traffic.

- Switch A / B / C (Cisco 2960)
Distributes the network connection to all devices inside the campus and separates Admin and Clinical staff into separate VLANs.

- PC-x1 / PC-x2 (VLAN 10 Admin)
Admin staff devices reception, billing, scheduling kept on their own VLAN so they can't access clinical systems.

- PC-x3 (VLAN 20 Clinical)
Clinical staff devices doctors and nurses kept isolated from admin so patient data is only accessible to authorised medical staff.

- VPN Tunnel (IPSec AES-256)
An encrypted pipe running over the public internet between campuses anyone intercepting the traffic sees nothing but scrambled data.

We contributed by updating the GitHub content and also working on the network design after the Zoom meeting with the mentor. Based on the feedback given, made changes in the diagram using draw.io, especially improving the VPN structure, firewall placement, and overall layout of the design , helped in refining the diagram to make it more clear and aligned with the requirements discussed during the meeting.

We also reviewed our previous mistakes and made sure not to repeat them. Compared to earlier weeks, our communication has improved and everyone is contributing their ideas, which helped us move forward more effectively.

Now our updated design is much more structured and clearly shows how the campuses are connected using VPN over the internet, with a central firewall and servers placed in the CBD campus.

This design took multiple discussions, trial and error, and continuous improvements based on feedback. We believe this version better meets the project requirements and mentor expectations.

Design 2 - 

<img width="1930" height="1481" alt="Networkdesignfinal drawio" src="https://github.com/user-attachments/assets/e312c3da-90ed-4e14-b27a-5bbeb148da7d" />

Please click this link to access the file -> [Networkdesignfinal.drawio](https://github.com/user-attachments/files/27353620/Networkdesignfinal.drawio)

## Conclusion
Design 1 - The Melbourne Metro Health Network (MMHN) connects three hospital campuses across Melbourne, Clayton, Mernda, and CBD, using a hub and spoke design built around a single central firewall that inspects all network traffic. Each campus runs an independent LAN segmented into Admin (VLAN 10) and Clinical (VLAN 20) zones, with inter-campus communication secured through IPSec AES-256 VPN tunnels over the public internet. At the hub, a Database Server holds all patient records as a centralised source of truth, while a Shared Campus Server handles authentication and file services for all three sites. The result is a simple, secure, and cost-effective network that protects sensitive patient data, minimises unnecessary hardware, and meets the requirements of a modern healthcare organisation.

Design 2 - In this update, we made several important improvements to our network design based on the mentor’s feedback. The main change was correcting the VPN structure by clearly showing that all campus connections go through the internet instead of direct links. This helped make the design more realistic and aligned with how actual networks operate.
We also centralised the architecture by making the CBD campus the main hub of the network. A single firewall was placed in the CBD campus to act as the main security point, ensuring that all incoming and outgoing traffic is filtered properly. The servers were moved into a dedicated DMZ zone to improve security and separate them from the internal network.
Additionally, we improved the internal structure by adding VLAN segmentation for different user groups such as admin, doctors, IoT devices, and guest Wi-Fi. This helps in better traffic management and network security.
Overall, the updated design is more clear, structured, and secure compared to the previous version. It now better represents a real-world network by using proper VPN implementation, centralised control, and secure server placement.
