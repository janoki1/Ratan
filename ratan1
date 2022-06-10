# Ratan
Joypurhat
Contacts
Permission in manifest
<uses-permission android:name="android.permission.READ_CONTACTS"></uses-permission>
Executing the contacts application using intent
Intent intent = new Intent(Intent.ACTION_VIEW);
intent.setData(Uri.parse("content://contacts/people/" ));
startActivity(intent);
Using intent to display a contact with id
Intent intent = new Intent(Intent.ACTION_VIEW);
intent.setData(Uri.parse("content://contacts/people/"+id )); startActivity(intent);
Query the contacts tables from your application
Querying the contacts table
ContentResolver cr = getContentResolver();
   
Cursor cur = cr.query(
                   ContactsContract.Contacts.CONTENT_URI, null,null, null, null);
                    
if (cur.getCount() > 0) {
          while (cur.moveToNext()) {
                   String id = cur.getString(
                             cur.getColumnIndex(ContactsContract.Contacts._ID));
                   String name = cur.getString(
                             cur.getColumnIndex(ContactsContract.Contacts.DISPLAY_NAME));
                    
//check if exists in the phones table
                   if (Integer.parseInt(
                                                cur.getString(
                                                          cur.getColumnIndex(
                                                                             ContactsContract.Contacts.HAS_PHONE_NUMBER))) > 0) {
                             queryPhonesTable(id, name);
                   }
          }
}

