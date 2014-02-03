%include 'WIN32N.INC'
EXTERN MessageBoxA
Import MessageBoxA user32.dll
EXTERN ExitProcess
Import ExitProcess kernel32.dll
SECTION CODE USE32 CLASS=CODE
..start:
	push UINT MB_OK
	push LPCTSTR title
	push LPCTSTR banner
	push HWND NULL
	call [MessageBoxA]
	push UINT NULL
	call [ExitProcess]
SECTION DATA USE32 CLASS=DATA
	banner db 'Hello, world!',0xD,0xA,0
	title db 'Hello',0
