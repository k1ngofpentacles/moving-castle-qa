# QA: Horizons H7-4: keystones and gateways

Chapter id `horizons_h7_4`, 9 checks. In game this is the FTB Quests chapter **QA: Horizons H7-4: keystones and gateways**; each check there has a green "Set up this check" line that builds its test site.

## 1. Imprint a keystone

Check id: `horizons_h7_4.keystone_imprint`

**Steps**

1. You stand two blocks from the rift of a forge plane with two blank keystones.
2. Walk into the rift. Use a blank keystone on a block that is not the vortex at the centre, then on the vortex. Read the imprinted keystone's name and tooltip.
3. Run /thaumichorizons plane preset storm, go in there too and imprint the second keystone: the two should differ in tint.

**Expect**

- [ ] Only the exit vortex imprints. A blank keystone reads Blank Planar Keystone with no tooltip and no tint; an imprinted one reads Planar Keystone with the plane's name below and the keystone art tinted in the plane's colour.
- [ ] Two planes give two colours.

<sub>Already covered by automated pack tests: `imprint_accepts_only_a_planes_exit_vortex`, `the_plane_key_round_trips_and_names_the_stack`</sub>

## 2. Build the frame and slot the keystone

Check id: `horizons_h7_4.frame_and_receptacle`

**Steps**

1. You stand in front of a finished gateway frame five blocks ahead (the Keystone Receptacle top middle) and, two blocks ahead, the rift of a forge plane. Slot 1 holds a blank keystone.
2. Open the research Planar Gateways and compare its gateway page with the frame. Walk into the rift and imprint the keystone on the exit vortex, come back out.
3. Right-click the receptacle with the imprinted keystone. Take it out with an empty hand and put it back.

**Expect**

- [ ] The research page shows the same frame. The receptacle is an open iron-bound cube; with a keystone slotted a tinted cube shows in its middle, in the plane's colour; the keystone comes back to your hand.

<sub>Already covered by automated pack tests: `frame_x_aligned_is_recognised_and_one_wrong_block_fails`, `frame_z_aligned_is_recognised`, `the_keystone_goes_in_comes_out_and_drops_when_the_receptacle_breaks`, `the_research_entry_and_recipes_are_in_the_jar`</sub>

## 3. Open the gateway with a wand

Check id: `horizons_h7_4.open_cost`

**Steps**

1. You stand in front of a gateway frame with its receptacle and, two blocks ahead, the rift of a forge plane. Your hotbar holds an empty wand, a full wand and a blank keystone.
2. Imprint the keystone on the plane's exit vortex (walk through the rift), come back and slot it in the receptacle. Right-click the receptacle with the empty wand (should refuse), then with the full wand.
3. Try again with one wrong frame block (break a frame block first). Watch the vis, the frame and the sound when it opens.

**Expect**

- [ ] Too little vis: a message, nothing changes and nothing is drawn; same for a wrong frame block. With enough vis 250 of every primal is drawn (a little more or less depending on the cap), the frame blocks turn into carved gateway blocks, a violet portal fills the middle and the wand sound plays.

<sub>Already covered by automated pack tests: `the_cost_is_250_of_every_primal_and_a_short_wand_loses_nothing`, `converting_and_closing_replace_every_cell`, `a_gateway_with_no_plane_loaded_changes_nothing_and_costs_nothing`</sub>

## 4. Walk through, both ways

Check id: `horizons_h7_4.walk_through`

**Steps**

1. You stand in front of a gateway frame with its receptacle and, two blocks ahead, the rift of a forge plane. Your hotbar holds a full wand and a blank keystone.
2. Imprint the keystone in the plane, slot it in the receptacle and open the gateway with the wand. Walk into the open gateway, look around where you arrive, then walk back into the plane's portal.
3. Rebuild the frame turned the other way (X and Z) and repeat.

**Expect**

- [ ] You arrive inside a 3x3 portal on the edge of the plane, facing inward, with a short open alcove ahead (a deviation: the original had you stand with your head in the shell). Stepping out and back into that portal returns you to the receptacle's gateway, in the middle of the portal, facing out. No bouncing back and forth.
- [ ] Both frame alignments work.

<sub>Already covered by automated pack tests: `plane_side_portals_sit_on_the_matching_side_with_boundary_behind`</sub>

## 5. Four gateways to one plane

Check id: `horizons_h7_4.four_gateways`

**Steps**

1. You stand in front of one gateway frame with its receptacle and a forge plane's rift two blocks ahead. Your hotbar holds a full wand, five blank keystones, three more receptacles and the frame blocks for three more frames.
2. Imprint the keystones on the plane's exit vortex, open this gateway, build and open three more with keystones of that plane, then try a fifth. In the plane walk round to see the four portals.

**Expect**

- [ ] The fifth refuses with a message and draws no vis. The plane shows four portals, one on each side; each takes you to its own gateway.

<sub>Already covered by automated pack tests: `four_slots_open_and_the_fifth_is_refused`</sub>

## 6. Close it three ways

Check id: `horizons_h7_4.closing`

**Steps**

1. You stand in front of a gateway frame with its receptacle and a forge plane's rift two blocks ahead. Your hotbar holds a full wand, a blank keystone and a spare receptacle.
2. Imprint the keystone, slot it, open the gateway. Take the keystone out with an empty hand. Reopen it and break the receptacle. Reopen with the spare receptacle and break one frame block. Each time watch the plane's portal.
3. Open it once more, stand in the plane at its portal while a frame cell is removed (/setblock a frame block to air from outside), and walk into the portal.

**Expect**

- [ ] Every way closes it: frame blocks return to Advanced Alchemical Construct and Ancient Stone, the portal is gone, the craft-fail sound plays, the keystone drops or returns, and the plane's portal becomes solid boundary again.
- [ ] A portal left open after the frame is gone sends you to the plane's arrival pad with a message and seals itself; the slot is free again.

<sub>Already covered by automated pack tests: `breaking_a_frame_block_closes_the_gateway`, `a_stale_slot_is_not_live`</sub>

## 7. No gateways in the plane or the Outer Lands

Check id: `horizons_h7_4.ban`

**Steps**

1. A forge plane's rift is two blocks ahead of you. Your hotbar holds a full wand and the blocks for two frames (see Planar Gateways for the layout).
2. Run /execute in thaumaturge:outer_lands run tp @s 0 100 0, build a frame there and wave the wand at its receptacle. Then come back, walk into the plane, build a frame with the kit blocks and do the same.

**Expect**

- [ ] A message that a gateway cannot be opened here; the frame is unchanged and no vis is drawn.

<sub>Already covered by automated pack tests: `the_ban_covers_the_plane_and_the_outer_lands_only`</sub>

## 8. Keystones for a second player

Check id: `horizons_h7_4.multiplayer`

**Steps**

1. You stand in front of a gateway frame and a forge plane's rift. Host a LAN game and have a second player join (they need the gateway research too).
2. Imprint the keystone in the plane, slot it, open the gateway, and have the second player look at the keystone (give them one), at the receptacle holding it, and walk through the gateway.

**Expect**

- [ ] The second player sees the plane's name and colour on the keystone and the tinted cube in the receptacle (the original showed white and no name on any client but the host).

<sub>Already covered by automated pack tests: `the_plane_key_round_trips_and_names_the_stack`</sub>

## 9. How the portal looks and sounds

Check id: `horizons_h7_4.portal_look`

**Steps**

1. You stand in front of a gateway frame and a forge plane's rift. Your hotbar holds a full wand and a blank keystone.
2. Imprint the keystone in the plane, slot it in the receptacle and open the gateway. Stand a few blocks from it and watch it; step through.

**Expect**

- [ ] The portal looks like a vanilla portal sheet with portal particles; the frame blocks show carved corner and edge art. Opening plays the wand sound, closing the craft-fail sound.

---
Report each check with the [QA report form](../../../issues/new?template=qa-report.yml) (chapter `horizons_h7_4`).
