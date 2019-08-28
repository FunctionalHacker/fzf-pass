#!/usr/bin/env bash

cd $HOME/.password-store
PASSFILE=$(tree -Ffi | grep '.gpg' | sed 's/.gpg$//g' | sed 's/^..//' | fzf)

if [ -z "$PASSFILE" ]; then
	exit 0
fi

PASSDATA="$(pass $PASSFILE)"
USRNAME="$(echo "$PASSDATA" | grep "username:" | cut -d' ' -f2-)"
PASS="$(echo "$PASSDATA" | head -n 1)"
URL="$(echo $PASSDATA | grep url: | cut -d' ' -f2-)"

RESP=$(cat <<EOF | fzf
Autotype
Username
Password
OTP
URL
EOF
);

swaymsg move container to workspace 9

case "$RESP" in
	Autotype)
		ydotool type "$USRNAME" && ydotool key Tab && ydotool type "$PASS" && ydotool key Enter
		;;
	Username)
		ydotool type "$USRNAME"
		;;
	Password)
		ydotool type "$PASS"
		;;
	OTP)
		ydotool type "$(pass otp $PASSFILE)"
		;;
	URL)
		ydotool type "$URL"
		;;
	*)
		exit 1
esac
