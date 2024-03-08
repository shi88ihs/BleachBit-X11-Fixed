##NOTE: Download this python file and put it in /bin or /usr/bin or keep in Downloads. Can name it bleachbit2 or bleachbitfixed with the .py ext. chmod +x to the file and run with python.

# BleachBit-X11-Fixed
Fixes Error:  bleachbit.Unix.is_display_protocol_wayland_and_root_not_allowed()

Excatly the same code as the real BleachBit. But Commented out this code so it would work with X11 and not throw this error: 

Error that is encountered if the code is run on a X11 System:


user@sys> bleachbit

Traceback (most recent call last):
  File "/usr/bin/bleachbit", line 40, in <module>
    bleachbit.Unix.is_display_protocol_wayland_and_root_not_allowed()
  File "/usr/share/bleachbit/Unix.py", line 746, in is_display_protocol_wayland_and_root_not_allowed
    bleachbit.Unix.is_linux_display_protocol_wayland() and
    ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/usr/share/bleachbit/Unix.py", line 732, in is_linux_display_protocol_wayland
    session = result[1].split('\n')[1].strip().split(' ')[0]
              ~~~~~~~~~~~~~~~~~~~~~^^^
IndexError: list index out of range



Code Commented out to Fix the crashing:

 # Commented out the Wayland root check to prevent the script from exiting
    # if (
    #     bleachbit.Unix.is_display_protocol_wayland_and_root_not_allowed()
    # ):
    #     print(_('To run a GUI application on Wayland with root, allow access with this command:\n'
    #           'xhost si:localuser:root\n'
    #             'See more about xhost at https://docs.bleachbit.org/doc/frequently-asked-questions.html'))
    #     sys.exit(1)


