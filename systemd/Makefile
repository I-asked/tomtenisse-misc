all:


install-systemd-chain: startup-precondition.path startup-precondition.target miral-kiosk.service b2g.service
	install -d $(DESTDIR)/lib/systemd/user/
	install -d $(DESTDIR)/lib/systemd/user/default.target.wants/
	install -d $(DESTDIR)/lib/systemd/user/startup-precondition.target.wants/
	install -d $(DESTDIR)/lib/systemd/user/miral-kiosk.service.wants/
	cp $^ $(DESTDIR)/lib/systemd/user/
	ln -sf ../startup-precondition.path $(DESTDIR)/lib/systemd/user/default.target.wants/startup-precondition.path
	ln -sf ../miral-kiosk.service $(DESTDIR)/lib/systemd/user/startup-precondition.target.wants/miral-kiosk.service
	ln -sf ../b2g.service $(DESTDIR)/lib/systemd/user/miral-kiosk.service.wants/b2g.service


install: install-systemd-chain


.PHONY: all install-systemd-chain install
