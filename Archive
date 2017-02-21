// Copy a doc to a folder with a timestamp in the file name.

DOCTOARCHIVE_ID = 'xxxxxxxxxxxxxxxxxxxxxxxxxxx'; // Change to your doc ID
FOLDERTOARCHIVE_ID = 'xxxxxxxxxxxxxxxxxxxxxxxxxxx'; // Change to your folder ID. Notice that this folder should exist before execution.
MAIL = 'example@gmail.com'; // Change to your mail.

// You can set a weekly trigger to archiveDoc() and it will create an useful history of files.
function archiveDoc() {

  archive(DOCTOARCHIVE_ID, FOLDERTOARCHIVE_ID, MAIL);
  
}

// Archive a copy of a document (doc) into folder (folder) and send an email (mails)
function archive(doc, folder, mails) {

  // Open the file
  doc_current = DriveApp.getFileById(doc);
  doc_name = doc_current.getName();

  // Calculate date
  var today = new Date(); 
  var todayformat = today.getFullYear()+"-"+(today.getMonth()+1)+"-"+today.getDate();

  // Open the folder
  var datafolder = DriveApp.getFolderById(folder);
  
  // Create the copy
  doc_current.makeCopy(doc_name + ' ' + todayformat, datafolder);
  
  // Send an email 
  var message = '\nFile archived: ' + doc_name + ' ' + todayformat + ' under folder ' + datafolder.getName() + '.\n\nhttps://docs.google.com/a/emergya.com/#folders/' + folder;
  var subject = 'Notification - ' + doc_name + ' ' + todayformat + ' archived';
  MailApp.sendEmail(mails, subject, message );
  
}
