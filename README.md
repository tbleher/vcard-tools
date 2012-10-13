Some small tools to manage addressbooks
=======================================

These tools grew out of the desire to have a GUI tool to manage my address book,
while still being able to quickly access address data from the command line.

I like KAddressBook for editing addresses, but I do not want to trust it blindly
with my data. I regularly export my address book data to ~/.addressbook.vcf.

My workflow:

* Check for changes using `diff_vcard`. If the changes look sane, export them
  using `set_vard`.

* If any email addresses changed, export a new mutt alises file. This is done
  using `diff_aliases` and `set_aliases` in .mutt. I store the generated aliases
  file in ~/.mutt/aliases_generated. I also have another alias file
  ~/.mutt/alias which I modify manually (e.g. for lists of addresses).

* To quickly query an address from the command line, I use `vgrep <pattern>`.

* Sometimes I need an excel sheet containing some specific addresses. This can
  be done using e.g. `vgrep 'ORG:Acme Corp' | vcard2csv -e - | csv2xls acme.xls`
  'vcard2csv -e -' converts the given vcf file (in this case - aka stdin) to a
  csv file. -e means to store email addressses in the list. csv2xls converts
  this csv file to an excel sheet.

These tools are released under the GNU GPL v2, or at your option, any later
version.

Thomas Bleher, <ThomasBleher@gmx.de>

