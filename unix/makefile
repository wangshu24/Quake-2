
CFLAGS = -c
LDFLAGS =
ODIR = baddir

EXEBASE = quake2
EXE = $(ODIR)/quake2
all: $(EXE)

#----------------------------------------------------------------------

SERVERFILES = $(ODIR)/sv_ccmds.o $(ODIR)/sv_ents.o $(ODIR)/sv_game.o $(ODIR)/sv_init.o $(ODIR)/sv_main.o $(ODIR)/sv_send.o $(ODIR)/sv_user.o $(ODIR)/sv_world.o

CLIENTFILES = $(ODIR)/cl_demo.o $(ODIR)/cl_ents.o $(ODIR)/cl_fx.o $(ODIR)/cl_input.o $(ODIR)/cl_inv.o $(ODIR)/cl_main.o $(ODIR)/cl_parse.o $(ODIR)/cl_tent.o $(ODIR)/console.o $(ODIR)/keys.o $(ODIR)/menu.o $(ODIR)/qmenu.o $(ODIR)/screen.o $(ODIR)/scr_cin.o $(ODIR)/snd_dma.o $(ODIR)/snd_mem.o $(ODIR)/snd_mix.o $(ODIR)/view.o

# commonfiles are used by both client and server
COMMONFILES = $(ODIR)/cmd.o $(ODIR)/cmodel.o $(ODIR)/cvar.o $(ODIR)/files.o $(ODIR)/md4.o $(ODIR)/net_chan.o $(ODIR)/net_udp.o

REFGLFILES = $(ODIR)/gl_draw.o $(ODIR)/gl_inter.o $(ODIR)/gl_light.o $(ODIR)/gl_math.o $(ODIR)/gl_mesh.o $(ODIR)/gl_model.o $(ODIR)/gl_rmain.o $(ODIR)/gl_rmisc.o $(ODIR)/gl_rsurf.o $(ODIR)/gl_textr.o $(ODIR)/gl_warp.

REFSOFTFILES = $(ODIR)/r_aclip.o $(ODIR)/r_alias.o $(ODIR)/r_bsp.o $(ODIR)/r_draw.o $(ODIR)/r_edge.o $(ODIR)/r_image.o $(ODIR)/r_light.o $(ODIR)/r_main.o $(ODIR)/r_misc.o $(ODIR)/r_model.o $(ODIR)/r_part.o $(ODIR)/r_polyse.o $(ODIR)/r_poly.o $(ODIR)/r_rast.o $(ODIR)/r_scan.o $(ODIR)/r_sprite.o $(ODIR)/r_surf.o

# sharedfiles are included in EVERY dll
SHAREDFILES = $(ODIR)/q_shared

#----------------------------------------------------------------------

_next:
	make "CFLAGS = -c -Wall -g -O" "ODIR = next"
	
_irix:
	make "CFLAGS = -c -O2 -Xcpluscomm -woff 513 -woff 594 -woff 596" "LDFLAGS = -Ofast=ip32_10k" "ODIR = irix"
	
_irixdebug:
	make "CFLAGS = -c -O2 -g -Xcpluscomm" "LDFLAGS = -g" "ODIR = irix"
		
clean:
	rm -f next/*.o next/$(EXEBASE)
	rm -f irix/*.o irix/$(EXEBASE)

#----------------------------------------------------------------------

FILES = $(SERVERFILES) $(COMMONFILES) $(CLIENTFILES) $(REFSOFTFILES) $(SHAREDFILES)

$(EXE) : $(FILES)
	cc -o $(EXE) $(LDFLAGS) $(FILES) -lm

#----------------------------------------------------------------------

$(ODIR)/q_shared.o : ../qcommon/q_shared.c
	cc $(CFLAGS) -o $@ $?

#----------------------------------------------------------------------

$(ODIR)/sv_ccmds.o : ../server/sv_ccmds.c
	cc $(CFLAGS) -o $@ $?

$(ODIR)/sv_ents.o : ../server/sv_ents.c
	cc $(CFLAGS) -o $@ $?

$(ODIR)/sv_game.o : ../server/sv_game.c
	cc $(CFLAGS) -o $@ $?

$(ODIR)/sv_init.o : ../server/sv_init.c
	cc $(CFLAGS) -o $@ $?

$(ODIR)/sv_main.o : ../server/sv_main.c
	cc $(CFLAGS) -o $@ $?

$(ODIR)/sv_send.o : ../server/sv_send.c
	cc $(CFLAGS) -o $@ $?

$(ODIR)/sv_user.o : ../server/sv_user.c
	cc $(CFLAGS) -o $@ $?

$(ODIR)/sv_world.o : ../server/sv_world.c
	cc $(CFLAGS) -o $@ $?

#----------------------------------------------------------------------

$(ODIR)/cl_demo.o : ../client/cl_demo.c
	cc $(CFLAGS) -E $? | tr -d '\015' > /tmp/temp.i
	cc $(CFLAGS) -o $@ /tmp/temp.i

$(ODIR)/cl_ents.o : ../client/cl_ents.c
	cc $(CFLAGS) -E $? | tr -d '\015' > /tmp/temp.i
	cc $(CFLAGS) -o $@ /tmp/temp.i

$(ODIR)/cl_fx.o : ../client/cl_fx.c
	cc $(CFLAGS) -E $? | tr -d '\015' > /tmp/temp.i
	cc $(CFLAGS) -o $@ /tmp/temp.i

$(ODIR)/cl_input.o : ../client/cl_input.c
	cc $(CFLAGS) -E $? | tr -d '\015' > /tmp/temp.i
	cc $(CFLAGS) -o $@ /tmp/temp.i

$(ODIR)/cl_inv.o : ../client/cl_inv.c
	cc $(CFLAGS) -E $? | tr -d '\015' > /tmp/temp.i
	cc $(CFLAGS) -o $@ /tmp/temp.i

$(ODIR)/cl_main.o : ../client/cl_main.c
	cc $(CFLAGS) -E $? | tr -d '\015' > /tmp/temp.i
	cc $(CFLAGS) -o $@ /tmp/temp.i

$(ODIR)/cl_parse.o : ../client/cl_parse.c
	cc $(CFLAGS) -E $? | tr -d '\015' > /tmp/temp.i
	cc $(CFLAGS) -o $@ /tmp/temp.i

$(ODIR)/cl_tent.o : ../client/cl_tent.c
	cc $(CFLAGS) -E $? | tr -d '\015' > /tmp/temp.i
	cc $(CFLAGS) -o $@ /tmp/temp.i

$(ODIR)/console.o : ../client/console.c
	cc $(CFLAGS) -E $? | tr -d '\015' > /tmp/temp.i
	cc $(CFLAGS) -o $@ /tmp/temp.i

$(ODIR)/keys.o : ../client/keys.c
	cc $(CFLAGS) -E $? | tr -d '\015' > /tmp/temp.i
	cc $(CFLAGS) -o $@ /tmp/temp.i

$(ODIR)/menu.o : ../client/menu.c
	cc $(CFLAGS) -E $? | tr -d '\015' > /tmp/temp.i
	cc $(CFLAGS) -o $@ /tmp/temp.i

$(ODIR)/qmenu.o : ../client/qmenu.c
	cc $(CFLAGS) -E $? | tr -d '\015' > /tmp/temp.i
	cc $(CFLAGS) -o $@ /tmp/temp.i

$(ODIR)/sbar2.o : ../client/sbar2.c
	cc $(CFLAGS) -E $? | tr -d '\015' > /tmp/temp.i
	cc $(CFLAGS) -o $@ /tmp/temp.i

$(ODIR)/screen.o : ../client/screen.c
	cc $(CFLAGS) -E $? | tr -d '\015' > /tmp/temp.i
	cc $(CFLAGS) -o $@ /tmp/temp.i

$(ODIR)/scr_cin.o : ../client/scr_cin.c
	cc $(CFLAGS) -E $? | tr -d '\015' > /tmp/temp.i
	cc $(CFLAGS) -o $@ /tmp/temp.i

$(ODIR)/snd_dma.o : ../client/snd_dma.c
	cc $(CFLAGS) -E $? | tr -d '\015' > /tmp/temp.i
	cc $(CFLAGS) -o $@ /tmp/temp.i

$(ODIR)/snd_mem.o : ../client/snd_mem.c
	cc $(CFLAGS) -E $? | tr -d '\015' > /tmp/temp.i
	cc $(CFLAGS) -o $@ /tmp/temp.i

$(ODIR)/snd_mix.o : ../client/snd_mix.c
	cc $(CFLAGS) -E $? | tr -d '\015' > /tmp/temp.i
	cc $(CFLAGS) -o $@ /tmp/temp.i

$(ODIR)/view.o : ../client/view.c
	cc $(CFLAGS) -E $? | tr -d '\015' > /tmp/temp.i
	cc $(CFLAGS) -o $@ /tmp/temp.i
	
#----------------------------------------------------------------------

$(ODIR)/cmd.o : ../qcommon/cmd.c
	cc $(CFLAGS) -E $? | tr -d '\015' > /tmp/temp.i
	cc $(CFLAGS) -o $@ /tmp/temp.i

$(ODIR)/cmodel.o : ../qcommon/cmodel.c
	cc $(CFLAGS) -E $? | tr -d '\015' > /tmp/temp.i
	cc $(CFLAGS) -o $@ /tmp/temp.i

$(ODIR)/cvar.o : ../qcommon/cvar.c
	cc $(CFLAGS) -E $? | tr -d '\015' > /tmp/temp.i
	cc $(CFLAGS) -o $@ /tmp/temp.i

$(ODIR)/files.o : ../qcommon/files.c
	cc $(CFLAGS) -E $? | tr -d '\015' > /tmp/temp.i
	cc $(CFLAGS) -o $@ /tmp/temp.i

$(ODIR)/md4.o : ../qcommon/md4.c
	cc $(CFLAGS) -E $? | tr -d '\015' > /tmp/temp.i
	cc $(CFLAGS) -o $@ /tmp/temp.i

$(ODIR)/net_chan.o : ../qcommon/net_chan.c
	cc $(CFLAGS) -E $? | tr -d '\015' > /tmp/temp.i
	cc $(CFLAGS) -o $@ /tmp/temp.i

$(ODIR)/net_udp.o : ../qcommon/net_udp.c
	cc $(CFLAGS) -E $? | tr -d '\015' > /tmp/temp.i
	cc $(CFLAGS) -o $@ /tmp/temp.i

$(ODIR)/sys_null.o : ../qcommon/sys_null.c
	cc $(CFLAGS) -E $? | tr -d '\015' > /tmp/temp.i
	cc $(CFLAGS) -o $@ /tmp/temp.i

#----------------------------------------------------------------------

$(ODIR)/gl_draw.o : ../ref_gl/gl_draw.c
	cc $(CFLAGS) -E $? | tr -d '\015' > /tmp/temp.i
	cc $(CFLAGS) -o $@ /tmp/temp.i

$(ODIR)/gl_inter.o : ../ref_gl/gl_inter.c
	cc $(CFLAGS) -E $? | tr -d '\015' > /tmp/temp.i
	cc $(CFLAGS) -o $@ /tmp/temp.i

$(ODIR)/gl_light.o : ../ref_gl/gl_light.c
	cc $(CFLAGS) -E $? | tr -d '\015' > /tmp/temp.i
	cc $(CFLAGS) -o $@ /tmp/temp.i

$(ODIR)/gl_math.o : ../ref_gl/gl_math.c
	cc $(CFLAGS) -E $? | tr -d '\015' > /tmp/temp.i
	cc $(CFLAGS) -o $@ /tmp/temp.i

$(ODIR)/gl_mesh.o : ../ref_gl/gl_mesh.c
	cc $(CFLAGS) -E $? | tr -d '\015' > /tmp/temp.i
	cc $(CFLAGS) -o $@ /tmp/temp.i

$(ODIR)/gl_model.o : ../ref_gl/gl_model.c
	cc $(CFLAGS) -E $? | tr -d '\015' > /tmp/temp.i
	cc $(CFLAGS) -o $@ /tmp/temp.i

$(ODIR)/gl_rmain.o : ../ref_gl/gl_rmain.c
	cc $(CFLAGS) -E $? | tr -d '\015' > /tmp/temp.i
	cc $(CFLAGS) -o $@ /tmp/temp.i

$(ODIR)/gl_rmisc.o : ../ref_gl/gl_rmisc.c
	cc $(CFLAGS) -E $? | tr -d '\015' > /tmp/temp.i
	cc $(CFLAGS) -o $@ /tmp/temp.i

$(ODIR)/gl_rsurf.o : ../ref_gl/gl_rsurf.c
	cc $(CFLAGS) -E $? | tr -d '\015' > /tmp/temp.i
	cc $(CFLAGS) -o $@ /tmp/temp.i

$(ODIR)/gl_textr.o : ../ref_gl/gl_textr.c
	cc $(CFLAGS) -E $? | tr -d '\015' > /tmp/temp.i
	cc $(CFLAGS) -o $@ /tmp/temp.i

$(ODIR)/gl_warp.o : ../ref_gl/gl_warp.c
	cc $(CFLAGS) -E $? | tr -d '\015' > /tmp/temp.i
	cc $(CFLAGS) -o $@ /tmp/temp.i

#----------------------------------------------------------------------

$(ODIR)/r_aclip.o : ../ref_soft/r_aclip.c
	cc $(CFLAGS) -E $? | tr -d '\015' > /tmp/temp.i
	cc $(CFLAGS) -o $@ /tmp/temp.i

$(ODIR)/r_alias.o : ../ref_soft/r_alias.c
	cc $(CFLAGS) -E $? | tr -d '\015' > /tmp/temp.i
	cc $(CFLAGS) -o $@ /tmp/temp.i

$(ODIR)/r_bsp.o : ../ref_soft/r_bsp.c
	cc $(CFLAGS) -E $? | tr -d '\015' > /tmp/temp.i
	cc $(CFLAGS) -o $@ /tmp/temp.i

$(ODIR)/r_draw.o : ../ref_soft/r_draw.c
	cc $(CFLAGS) -E $? | tr -d '\015' > /tmp/temp.i
	cc $(CFLAGS) -o $@ /tmp/temp.i

$(ODIR)/r_edge.o : ../ref_soft/r_edge.c
	cc $(CFLAGS) -E $? | tr -d '\015' > /tmp/temp.i
	cc $(CFLAGS) -o $@ /tmp/temp.i

$(ODIR)/r_image.o : ../ref_soft/r_image.c
	cc $(CFLAGS) -E $? | tr -d '\015' > /tmp/temp.i
	cc $(CFLAGS) -o $@ /tmp/temp.i

$(ODIR)/r_light.o : ../ref_soft/r_light.c
	cc $(CFLAGS) -E $? | tr -d '\015' > /tmp/temp.i
	cc $(CFLAGS) -o $@ /tmp/temp.i

$(ODIR)/r_main.o : ../ref_soft/r_main.c
	cc $(CFLAGS) -E $? | tr -d '\015' > /tmp/temp.i
	cc $(CFLAGS) -o $@ /tmp/temp.i

$(ODIR)/r_misc.o : ../ref_soft/r_misc.c
	cc $(CFLAGS) -E $? | tr -d '\015' > /tmp/temp.i
	cc $(CFLAGS) -o $@ /tmp/temp.i

$(ODIR)/r_model.o : ../ref_soft/r_model.c
	cc $(CFLAGS) -E $? | tr -d '\015' > /tmp/temp.i
	cc $(CFLAGS) -o $@ /tmp/temp.i

$(ODIR)/r_part.o : ../ref_soft/r_part.c
	cc $(CFLAGS) -E $? | tr -d '\015' > /tmp/temp.i
	cc $(CFLAGS) -o $@ /tmp/temp.i

$(ODIR)/r_polyse.o : ../ref_soft/r_polyse.c
	cc $(CFLAGS) -E $? | tr -d '\015' > /tmp/temp.i
	cc $(CFLAGS) -o $@ /tmp/temp.i

$(ODIR)/r_poly.o : ../ref_soft/r_poly.c
	cc $(CFLAGS) -E $? | tr -d '\015' > /tmp/temp.i
	cc $(CFLAGS) -o $@ /tmp/temp.i

$(ODIR)/r_rast.o : ../ref_soft/r_rast.c
	cc $(CFLAGS) -E $? | tr -d '\015' > /tmp/temp.i
	cc $(CFLAGS) -o $@ /tmp/temp.i

$(ODIR)/r_scan.o : ../ref_soft/r_scan.c
	cc $(CFLAGS) -E $? | tr -d '\015' > /tmp/temp.i
	cc $(CFLAGS) -o $@ /tmp/temp.i

$(ODIR)/r_sprite.o : ../ref_soft/r_sprite.c
	cc $(CFLAGS) -E $? | tr -d '\015' > /tmp/temp.i
	cc $(CFLAGS) -o $@ /tmp/temp.i

$(ODIR)/r_surf.o : ../ref_soft/r_surf.c
	cc $(CFLAGS) -E $? | tr -d '\015' > /tmp/temp.i
	cc $(CFLAGS) -o $@ /tmp/temp.i
	
#----------------------------------------------------------------------

