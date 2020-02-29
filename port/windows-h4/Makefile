# Makefile for windows-h4 examples
BTSTACK_ROOT ?= ../..

CORE += main.c btstack_stdin_windows.c

COMMON  += \
			btstack_run_loop_windows.c   \
			hci_transport_h4.c           \
			btstack_uart_block_windows.c \
			le_device_db_fs.c            \
			btstack_link_key_db_fs.c     \
            rijndael.c \
            wav_util.c 					\

# examples
include ${BTSTACK_ROOT}/example/Makefile.inc

# CC = gcc-fsf-4.9
CFLAGS  += -g -Wall -Wmissing-prototypes -Wstrict-prototypes -Wshadow -Werror
# CFLAGS += -Werror

CFLAGS += -I${BTSTACK_ROOT}/platform/posix \
		  -I${BTSTACK_ROOT}/platform/windows \
		  -I${BTSTACK_ROOT}/platform/embedded \
          -I${BTSTACK_ROOT}/3rd-party/rijndael \
		  -I${BTSTACK_ROOT}/3rd-party/tinydir

VPATH += ${BTSTACK_ROOT}/3rd-party/rijndael

VPATH += ${BTSTACK_ROOT}/platform/windows
VPATH += ${BTSTACK_ROOT}/platform/posix

EXAMPLES = ${EXAMPLES_GENERAL} ${EXAMPLES_CLASSIC_ONLY} ${EXAMPLES_LE_ONLY} ${EXAMPLES_DUAL_MODE}
EXAMPLES += pan_lwip_http_server

# assume portaudio is installed in /usr/local
# CFLAGS  += -I/usr/local/include -DHAVE_PORTAUDIO
# LDFLAGS += -L/sw/lib -lportaudio

all: ${EXAMPLES}
