# makefile for rtkrcv

BINDIR = /usr/local/bin
SRC    = ../../../src

# for beagleboard
#CTARGET= -mfpu=neon -mfloat-abi=softfp -ffast-math
CTARGET = -DENAGLO -DENAQZS -DNFREQ=3

# for raspberry pi
#CTARGET= -DENAGLO -DENAQZS -DNFREQ=3 -march=armv6zk -mcpu=arm1176jzf-s -mtune=arm1176jzf-s -mfloat-abi=hard


# for big endian targets use:
#CTARGET += -DBIG_ENDIAN

# if target allows unaligned data acces to uint16_t, uint32_t and float, you may use this option
# to speed up serialisation by pointer casts.
#CTARGET += -DUNALIGNED_ACCESS

CFLAGS = -Wall -ggdb3 -O3 -Wcast-align -ansi -pedantic -I$(SRC) -DTRACE $(CTARGET)
LDLIBS  = -lm -lpthread

all        : rtkrcv
rtkrcv     : rtkrcv.o rtkcmn.o rtksvr.o rtkpos.o geoid.o solution.o lambda.o
rtkrcv     : sbas.o stream.o rcvraw.o rtcm.o preceph.o options.o pntpos.o ppp.o ppp_ar.o
rtkrcv     : novatel.o ublox.o ss2.o crescent.o skytraq.o gw10.o javad.o nvs.o
rtkrcv     : ephemeris.o rinex.o ionex.o rtcm2.o rtcm3.o rtcm3e.o stec.o rtkpos_gsi.o

rtkrcv.o   : ../rtkrcv.c
	$(CC) -c $(CFLAGS) ../rtkrcv.c
rtkcmn.o   : $(SRC)/rtkcmn.c
	$(CC) -c $(CFLAGS) $(SRC)/rtkcmn.c
rtksvr.o   : $(SRC)/rtksvr.c
	$(CC) -c $(CFLAGS) $(SRC)/rtksvr.c
rtkpos.o   : $(SRC)/rtkpos.c
	$(CC) -c $(CFLAGS) $(SRC)/rtkpos.c
geoid.o    : $(SRC)/geoid.c
	$(CC) -c $(CFLAGS) $(SRC)/geoid.c
solution.o : $(SRC)/solution.c
	$(CC) -c $(CFLAGS) $(SRC)/solution.c
lambda.o   : $(SRC)/lambda.c
	$(CC) -c $(CFLAGS) $(SRC)/lambda.c
sbas.o     : $(SRC)/sbas.c
	$(CC) -c $(CFLAGS) $(SRC)/sbas.c
stream.o   : $(SRC)/stream.c
	$(CC) -c $(CFLAGS) $(SRC)/stream.c
rcvraw.o : $(SRC)/rcvraw.c
	$(CC) -c $(CFLAGS) $(SRC)/rcvraw.c
rtcm.o     : $(SRC)/rtcm.c
	$(CC) -c $(CFLAGS) $(SRC)/rtcm.c
rtcm2.o    : $(SRC)/rtcm2.c
	$(CC) -c $(CFLAGS) $(SRC)/rtcm2.c
rtcm3.o    : $(SRC)/rtcm3.c
	$(CC) -c $(CFLAGS) $(SRC)/rtcm3.c
rtcm3e.o   : $(SRC)/rtcm3e.c
	$(CC) -c $(CFLAGS) $(SRC)/rtcm3e.c
preceph.o  : $(SRC)/preceph.c
	$(CC) -c $(CFLAGS) $(SRC)/preceph.c
options.o  : $(SRC)/options.c
	$(CC) -c $(CFLAGS) $(SRC)/options.c
pntpos.o   : $(SRC)/pntpos.c
	$(CC) -c $(CFLAGS) $(SRC)/pntpos.c
ppp.o      : $(SRC)/ppp.c
	$(CC) -c $(CFLAGS) $(SRC)/ppp.c
ppp_ar.o   : $(SRC)/ppp_ar.c
	$(CC) -c $(CFLAGS) $(SRC)/ppp_ar.c
novatel.o  : $(SRC)/rcv/novatel.c
	$(CC) -c $(CFLAGS) $(SRC)/rcv/novatel.c
ublox.o    : $(SRC)/rcv/ublox.c
	$(CC) -c $(CFLAGS) $(SRC)/rcv/ublox.c
ss2.o      : $(SRC)/rcv/ss2.c
	$(CC) -c $(CFLAGS) $(SRC)/rcv/ss2.c
crescent.o : $(SRC)/rcv/crescent.c
	$(CC) -c $(CFLAGS) $(SRC)/rcv/crescent.c
skytraq.o  : $(SRC)/rcv/skytraq.c
	$(CC) -c $(CFLAGS) $(SRC)/rcv/skytraq.c
gw10.o     : $(SRC)/rcv/gw10.c
	$(CC) -c $(CFLAGS) $(SRC)/rcv/gw10.c
javad.o    : $(SRC)/rcv/javad.c
	$(CC) -c $(CFLAGS) $(SRC)/rcv/javad.c
nvs.o      : $(SRC)/rcv/nvs.c
	$(CC) -c $(CFLAGS) $(SRC)/rcv/nvs.c
ephemeris.o: $(SRC)/ephemeris.c
	$(CC) -c $(CFLAGS) $(SRC)/ephemeris.c
rinex.o    : $(SRC)/rinex.c
	$(CC) -c $(CFLAGS) $(SRC)/rinex.c
ionex.o    : $(SRC)/ionex.c
	$(CC) -c $(CFLAGS) $(SRC)/ionex.c
stec.o     : $(SRC)/stec.c
	$(CC) -c $(CFLAGS) $(SRC)/stec.c
rtkpos_gsi.o: $(SRC)/rtkpos_gsi.c
	$(CC) -c $(CFLAGS) $(SRC)/rtkpos_gsi.c

rtkrcv.o   : $(SRC)/rtklib.h
rtkcmn.o   : $(SRC)/rtklib.h
rtksvr.o   : $(SRC)/rtklib.h
rtkpos.o   : $(SRC)/rtklib.h
geoid.o    : $(SRC)/rtklib.h
solution.o : $(SRC)/rtklib.h
lambda.o   : $(SRC)/rtklib.h
sbas.o     : $(SRC)/rtklib.h
rcvraw.o   : $(SRC)/rtklib.h
rtcm.o     : $(SRC)/rtklib.h
rtcm2.o    : $(SRC)/rtklib.h
rtcm3.o    : $(SRC)/rtklib.h
rtcm3e.o   : $(SRC)/rtklib.h
preceph.o  : $(SRC)/rtklib.h
options.o  : $(SRC)/rtklib.h
pntpos.o   : $(SRC)/rtklib.h
ppp.o      : $(SRC)/rtklib.h
novatel.o  : $(SRC)/rtklib.h
ublox.o    : $(SRC)/rtklib.h
ss2.o      : $(SRC)/rtklib.h
crescent.o : $(SRC)/rtklib.h
skytraq.o  : $(SRC)/rtklib.h
gw10.o     : $(SRC)/rtklib.h
javad.o    : $(SRC)/rtklib.h
ephemeris.o: $(SRC)/rtklib.h
rinex.o    : $(SRC)/rtklib.h
ionex.o    : $(SRC)/rtklib.h
stec.o     : $(SRC)/rtklib.h
rtkpos_gsi.o: $(SRC)/rtklib.h

install:
	cp rtkrcv $(BINDIR)

test1:
	./rtkrcv -t 4 -m 52001 -t 4

test2:
	./rtkrcv -p 2105 -m 52001

test3:
	./rtkrcv -o ../rtk_pb.conf

clean:
	rm -f rtkrcv rtkrcv.exe rtkrcv.nav *.o *.out *.trace

