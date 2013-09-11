import os

Import('xenv')
xenv = xenv.Clone()

xenv.UseBoost()
this_dir = os.path.join('#vendor', 'bson')
xenv.Append(CPPPATH = [this_dir, os.path.join(this_dir, 'src'), os.path.join(this_dir, 'src', 'util')])

sources = xenv.Glob(os.path.join('src', '*.cpp'))
sources += xenv.Glob(os.path.join('lib', '*.cpp'))
sources += xenv.Glob(os.path.join('lib', '*.c'))
sources += xenv.Glob(os.path.join('src', 'util', '*.cpp'))

bson_lib = xenv.BuildStaticLibrary('bson', sources)
SConscript(os.path.join('test', 'SConscript'), exports = ['xenv'])
Return(['bson_lib'])
