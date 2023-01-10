Linux README      7/14/01

To run the Half-Life/TFC decidated linux server, unpack the hlds_l3103.tar.gz
file into a directory on your server. If you have the 3.1.0.1 or 3.1.0.2 version 
installed, you can just unpack hlds_l3103upgrd.tar.zip into your current Half-Life server 
directory.

You will need to copy libhlwon.so on your library path(/etc/ld.so.conf). After 
doing this, you will need to run ldconfig to get Linux to recognize your changes 
to the ld.so.conf file.

Start the server by running ./hlds_run. After it has loaded, you are able to 
type commands into the server. During load time, you should see a message that 
says "WON Auth". This means that you are automatically registered on the 
Internet and people can start joining your game. 

If you don't see "WON Auth" but instead see "Auth Server", this means that 
you did not authenticate with the WON server either because you have an older
version of the server or you may not be able to reach the WON servers due to
a firewall or proxy.

After the server is loaded, you can set the number of allowed players with the 
maxplayers ("maxplayers 16") command. I would not recommend any more than 16
players on a 200mhz machine.

To start the maps, use the map command ("map cz2"). 

Changes for the Linux Server in version 3.1.0.7:
- DMC included in this release.
- Remote file exploit fixed.

Changes for the Linux Server in version 3.1.0.6:
- rcon protocol overhauled to prevent attacks.
- Logging standard added for TFC, HLDM, and Counter-Strike.
- New 'stat' command that shows the same information as the 'status' command, but is formatted for the screen and log file.
- rcon "say" quotes problem fixed.
- Disguise5 will no longer crash a Team Fortress server.
- Class limits at -1 crash fix.
- Added code to support the server variable 'sv_allowupload'
- Increased number of entries for banned IPs and banned WON IDs to 32768 (each).
- Changed what types of map resource files can be downloaded using .res files (to help mod authors).  We've changed from what types of files ARE allowed to what types of files AREN'T allowed.
- Added motdfile command.  Use hlds +motdfile <motd file name> in the command line or in your server.cfg to change the motd.txt file displayed on your server.
- Added logsdir command. Use hlds +logsdir <log file directory> in the command line or in your server.cfg to change the directory relative to the game directory where log files will be stored.
- Changed servercfgfile command.  Use hlds +servercfgfile <name of server.cfg> in the command line to change the server.cfg file used by your server.
- Changed mapcyclefile command.  This can now be run from the command line.
- Added mp_chattime cvar to specify how long players can chat at the end of a map before it cycles.  Default set to 10 (in seconds).
- Added tfc_playerid command.  This will toggle what information players on your server will see in their status bar.
	0 - players see all names listed in the status bar (with appropriate
team colors)
	1- players only see names for their teammates and hostages in the
status bar
	2- players do not see any names in the status bar (hostages included)
0 is the default
- Added tfc_spectchat.  This toggles if spectators can talk to normal clients, or just other spectators.

Changes for the Linux Server in version 3.1.0.5:

- Added a new TFC server cvar, tfc_spectchat, that will allow the server to regulate whether or not spectators can chat with players in the game.  When set to 0, spectators can only chat with other spectators.  When set to anything but 0, spectators can chat with everyone in the game.
- Merged a bit of missing code between versions 1.1.0.1 and 1.1.0.4
- Fixed "ERROR: SZ_GetSpace: overflow without FSB_ALLOWOVERFLOW set" crashing servers
- Fixed "ERROR: Dormant entity player is thinking!!" crashing servers
- Problem with fragmentation & reassembly of packets.
- Fixed the rcon 'say' command putting " " around every token
- Fixed small memory leak problem when using bots
- Put client's IP address back into the 'status' command
- If a player suicides (types "kill" in the console) while infected, the medic who infected him will get a kill.
- If a player changes teams while infected, the medic who infected him will get a kill.
- Fixed a bug where players could teamkill by shooting a rocket/grenade at a teammate and switching to specator mode.
- Fixed the "adm_deal", "adm_next", and "next" commands to properly cycle through the players in the server.
- Fixed the problem with some clients lagging for a round or two at the beginning of a map.
- Fixed the "listmaps" command so it displays all the maps (it was skipping the last one in the list).
- Fixed the problem with some entities not being reset correctly (i.e. on the map de_foption: could kill the terrorist team at the beginning of a round with a lightning strike).

Changes for the Linux Server in version 3.1.0.4:

- This update contains three new TF maps: Avanti, Flagrun, and Casbah.
- Pyro's burn damage increased in Team Fortress.
- Heavy Weapons Guy's chaingun damage reduced.
- All map resources can be downloaded from the game server now.  Refer to readme.txt for details.
- Anti-grenade triggers added to 2Fort spawn rooms.
- Team selection also available from class selection screen in Team Fortress.
- In-Game text upgraded.
- Last weapon used key persists over a player death now.
- Counter-Strike proxy cheat fixed.
- High framerate connection problem fixed.
- Cockroaches can now be killed in single player.
- 'Tell' command crash fixed in Team Fortress.
- Rcon buffer overflow fixed.

Changes for the Linux Server in version 3.1.0.3:

- Fixed spy burrowing into the ground.
- Fixed svc_bad connection problem.
- Fixed spy disguise as team 3/4 on two team maps.
- Fixed spy disguise crash.

Changes for the Linux Server in version 3.1.0.2:

- Fixed crash when clients have specific characters in their names.
- Fixed stout buffering problem.

Changes for the Linux Server in version 3.1.0.1:

- Fixed performance problem on ATI Rage video cards.
- Fixed 'Unassigned' in scoreboard bug.
- Fixed death messages being delayed when downloading a custom decal.
- Fixed 'Out of Handles' crash on dedicated server.
- Fixed bug where player models would be drawn incorrectly in Team Fortress 1.5
- Fixed fakelag exploit.
- Fixed mmx optimization.
- Restart command fixed on dedicated server.
- Fixed two flags in Dustbowl bug.
- Fixed longjump in Half-Life DM.
- Fixed spectator grenade exploit.
- Fixed changeteam grenade exploit.
- Fixed LoGADDRESS command.
 
Changes for the Linux Server in past versions:

- This update includes a complete rewrite of Half-Life's networking system.
- Three new maps included (Dustbowl, Epicenter, and Warpath).
- Engineer upgrades sentry gun immediately.
- Dispensers can be used by touching them.
- Spectator mode added.
- Number pad keys are now bindable independent.
- Support for mouse buttons 4 and 5.
- You will get a point in TFC for destroying an enemy sentry gun.
- Engineer can view other Engineer's sentry gun stats via HUD.
- Tell command added to TFC.
- The class of everyone on your team is available via the scoreboard.
- Grenade timer added to TFC.
- Updated netgraph, use net_graph 3
- TFC Manual updated with all information pertaining to this update.
- Console and in-game chat uses a True Type font.
- Player names are colored according to team in TFC when talking.
- MOTD length increased for server operators.
- "Say" no longer includes the server name in the 64 character limit.
- Various crash fixes.
- readline.so no longer required.
- Team 4 can now score on 4 player TFC maps.
- Fixed soldier's nail grenades in TFC.
- We are changing the version number of the server from 1.x.x.x to 3.x.x.x for 
  the Linux server to differentiate between the server and client releases.
- Typing 'version' at the server console will give you the version you are running.
- Server now allows banning by userid and WON id.  Refer to TFCServer.htm 
  located in your \halflife\tfc\manual directory.
- HTML TFC manual included with 3.0.1.3 Linux server with information on running a server.
- TFStats for Linux will be released in the very near future.
- TF Stats version 1.5 for Linux included.
- Half-Life setinfo bug fixed.
- Added better debugging code for TFC map makers.
- Fixed bug in trigger_changelevel.


Common Questions:

1) I start the server and nothing happens. 

After running ./hlds_l, you need to set the number of allowed players (see above) 
and start a map. You can do all of this from the command line as well:

./hlds_l -game tfc +maxplayers 16 +map cz2 


2) How do I start a TFC server?

Use the -game tfc option.

3) My server won't run, it's looking for:

a) libhlwon.so - see above.
b) readline.so - this is no longer needed. You have an old version of the server.

4) How do I start a lan server?

./hlds -nomaster +sv_lan 1

5) Where can I get help?

Subscribe to the one of the dedicated server mailing lists by sending mail to 
listadmin@valvesoftware.com with subscribe <the name of the mailing list below 
you want to subscribe to> in the message body.

hlds_announce@valvesoftware.com - general dedicated server announcements
hlds@valvesoftware.com - general dedicated server discussion
hlds_linux@valvesoftware.com - linux specific dedicated server discussion

Also, there are several user-run support sites on the net:
http://commands.halflife.org
http://www.pcgame.com/randy/tfc/console/all.htm
http://www.planethalflife.com/commands/

6) What are the server commands/cvars:

changelevel mapname - change map, maintain client connections
map mapname - change map, disconnect currently connected players
status - return the status of the server
restart - restart the server
exec file.cfg - execute a script file
quit - stop the server


Client Variables

cl_bob		Default:  0
cl_bobcycle	Default:  0
cl_bobup	Default:  0
cl_rollangle	Default:  2
cl_waterdist	Default:  4
cl_rollspeed	Default:  200


Multiplayer Variables

1 means on/allowed, 0 means off/disallowed.  
* means any integer is acceptable, 0 means no limit

mp_autocrosshair		Default:  1
mp_falldamage		Default:  1
mp_flashlight		Default:  0
mp_footsteps		Default:  1
mp_forcerespawn		Default:  1
mp_friendlyfire		Default:  0
mp_teamplay			Default:  0
mp_weaponstay		Default:  0
mp_allowmonsters		Default:  0
mp_fraglimit*		Default:  0
mp_timelimit*		Default:  0


Server Variables

sv_accelerate		Default:  10
sv_aim			Default:  1
sv_airaccelerate		Default:  10
sv_airmove			Default:  1
sv_allowdownload		Default:  1
sv_allowupload		Default:  1
sv_bounce			Default:  1
sv_challengetime		Default:  15
sv_cheats			Default:  0
sv_clienttrace		Default:  1
sv_clipmode			Default:  0
sv_friction			Default:  4
sv_gravity			Default:  800
sv_idealpitchscale	Default:  0
sv_language			Default:  0
sv_masterprint		Default:  1
sv_masterprinttime	Default:  5
sv_maxspectators		Default:  8
sv_maxspeed			Default:  320
sv_maxvelocity		Default:  2000
sv_netsize			Default:  0
sv_newunit			Default:  0
sv_password			Default:  0
sv_showcmd			Default:  0
sv_skyname			Default:  0
sv_spectalk			Default:  1
sv_spectator_password	Default:  0
sv_spectatormaxspeed	Default:  500
sv_stepsize			Default:  18
sv_stopspeed		Default:  100
sv_timeout			Default:  65
sv_upload_maxsize		Default:  0
sv_wateraccelerate	Default:  10
sv_wateramp			Default:  0
sv_waterfriction		Default:  1
sv_zmax			Default:  4096


Team Play Variables

team1_color		Default:  0  
team1_model		Default:  0  
team1_name		Default:  0  
team1_skin		Default:  0  
team2_color		Default:  0  
team2_model		Default:  0  
team2_name		Default:  0  
team2_skin		Default:  0  


brightness		Default:  0
chase_active	Default:  0
chase_back		Default:  100
chase_right		Default:  0
chase_up		Default:  16
clientport		Default:  27005
cmdline		Default:  0
con_notifytime	Default:  1
coop			Default:  0
crosshair		Default:  0
deathmatch		Default:  1
decalfrequency	Default:  30
developer		Default:  0
direct		Default:  0
displaysoundlist	Default:  0
edgefriction	Default:  2
fakelag		Default:  0
fakeloss		Default:  0
filterban		Default:  1
fps_lan		Default:  72
fps_modem		Default:  30
fps_single		Default:  72
gamma			Default:  2
host_framerate	Default:  0
host_killtime	Default:  0
host_speeds		Default:  0
HostMap		Default:  0
hostname		Default:  0
hostport		Default:  0
ip			Default:  0
ip_clientport	Default:  0
ip_hostport		Default:  0
ipx_clientport	Default:  0
ipx_hostport	Default:  0
lambert		Default:  1
lcd_x			Default:  0
lcd_yaw		Default:  0
lightgamma		Default:  2
mapcyclefile	Default:  0
netchokeloop	Default:  0
noip			Default:  0
noipx			Default:  1
pausable		Default:  1
pm_pushfix		Default:  0
port			Default:  27015
r_netgraph		Default:  0
rcon_password	Default:  0
registered		Default:  0
scr_ofsx		Default:  0
scr_ofsy		Default:  0
scr_ofsz		Default:  0
serverprofile	Default:  0
showdrop		Default:  0
showpackets		Default:  0
showtriggers	Default:  0
skill			Default:  1
sys_ticrate		Default:  0
texgamma		Default:  2
violence_ablood	Default:  1
violence_agibs	Default:  1
violence_hblood	Default:  1
violence_hgibs	Default:  1


View Variables

v_centermove	Default:  0
v_centerspeed	Default:  500
v_dark		Default:  0
v_idlescale		Default:  0
v_ipitch_cycle	Default:  1
v_ipitch_level	Default:  0
v_iroll_cycle	Default:  0
v_iroll_level	Default:  0
v_iyaw_cycle	Default:  2
v_iyaw_level	Default:  0
v_kickpitch		Default:  0
v_kickroll		Default:  0
v_kicktime		Default:  0



Please report any problems to erik@valvesoftware.com

Enjoy!


