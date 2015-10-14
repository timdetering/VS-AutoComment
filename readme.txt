'------------------------------------------------------------------------------
' Usage info
'
' To install:
'    1. Copy this file to 
'       %USERPROFILE%\My Documents\Visual Studio Projects\VSMacros\AutoCompl\AutoComplete.vsmacros
'    2. In VS.NET, go to menu Tools -> Macros -> Macro Explorer, and right click
'       on Macros in macro explorer. Then select "Load Macro Project ..."
'
' To Add shortcut key:
'    1. Go to menu Tools -> Customize -> Options -> Keyboard.
'    2. Add a shortcut key for command "Macros.AutoComplete.AutoComplete.Autocompl".
'       I use Alt+C.
'
' To use:
'    1. Open a c# or C++ file.
'    2. Move cursor to beginning of file, open a new line (keep cursor on the first line),
'       and then press Alt+C (or your own shortcut key). The macro will add copyright 
'       information.
'    3. Open a new line before any of your function, then press Alt+C. The macro will add
'       XML documentation for the function following the empty line.
'    4. Select a function name (or whatever text), then press Alt+C. The macro will add
'       a generic XML documentation.
'
'------------------------------------------------------------------------------

Samples:

1. Copyright

//-------------------------------------------------------------------
///
/// <company>Microsoft Corporation</company>
///
/// <copyright>Copyright (c) Microsoft Corporation 2002</copyright>
///
/// <summary>
///     Sid.cs
/// </summary>
///
/// <history>
///     <record date="10/21/2002" who="zzuo">Created</record>
/// </history>
///
//-------------------------------------------------------------------


2. Function XML Documentation

C++
Before

HRESULT DComCreateInstance
    (
    LPCWSTR szServer, // Remote Server
    REFCLSID rclsid,  // Class ID
    REFIID riid,      // Interface ID
    LPVOID * ppv      // Out pointer
    )
{
    ....
}

After

//-------------------------------------------------------------------
/// <summary>
/// DComCreateInstance
/// </summary>
/// <param name="szServer"></param>
/// <param name="rclsid"></param>
/// <param name="riid"></param>
/// <param name="ppv"></param>
//-------------------------------------------------------------------
HRESULT DComCreateInstance
    (
    LPCWSTR szServer, // Remote Server
    REFCLSID rclsid,  // Class ID
    REFIID riid,      // Interface ID
    LPVOID * ppv      // Out pointer
    )
{
    ....
}

C#
Before

        public object InvokeMethod(string methodName, object[]args)
        {
            MethodInfo mi = GetMethod(methodName);
            return mi.Invoke(instance, BindingFlags.Public|BindingFlags.InvokeMethod, null, args, null);
        }

After

        //-------------------------------------------------------------------
        /// <summary>
        /// InvokeMethod
        /// </summary>
        /// <param name="methodName"></param>
        /// <param name="args"></param>
        //-------------------------------------------------------------------
        public object InvokeMethod(string methodName, object[]args)
        {
            MethodInfo mi = GetMethod(methodName);
            return mi.Invoke(instance, BindingFlags.Public|BindingFlags.InvokeMethod, null, args, null);
        }