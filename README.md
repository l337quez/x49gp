# x49gp

Name:x49gp
Version:alpha
Release:1%{?dist}
Summary:Emulator of the newer Hewlett Packard Handheld Calculator Models with ARM CPU (HP49g  HP50).
License:GPLv2
URL:http://x49gp.sourceforge.net/
Group:Applications/Emulators

Source0:http://www.hpcalc.org/hp49/pc/emulators/x49gp.tar.gz

BuildRequires:gtk2-devel
BuildRequires:gcc
BuildRequires:subversion

Description
Emulator of the newer Hewlett-Packard handheld calculator models with
an ARM CPU (HP 49g  and HP 50g). This is a true ARM emulator running
on Unix, Linux, and MacOS Systems. Porting to Windows should be easy
as the GUI is based on GTK . The project is still in alpha state

%prep
%setup -c -q n %{name}

%build
%configure
autoreconf
make
make sdcard
make config

%install
make install DESTDIR=%{buildroot}

%files
�fattr(-,root,root,-)
%{_mandir}/man1/x49gp.tar.gz

%changelog
* Wed Feb 22 2014 Ronald Forero lt;L337.ronald AT gmail DOT com; -  alpha
- Initial build rpm 
