STAFF PERMISSIONS + PDF SAVE/SHARE UPDATE

Changes in this update:
1. Staff create/edit form now supports per-module View, Add, Edit and Delete permission chips for Student Records, Attendance, Fee Collection, Exams & Marks, Stock Management, Stock Giving, Syllabus and Date Sheet. Reports is View-only.
2. Permissions are saved in the staff record under modulePermissions. The existing permissions list is retained for compatibility with older records.
3. Staff login portal now displays the actions assigned to each module.
4. The four existing PDF output flows (fee voucher, class documents/DMC/cards/leaving certificate, student ID card, and school report) now call Printing.sharePdf. Android's share chooser can be used to save/download or share the PDF instead of relying on the failing Android print-preview flow.

Important limitations:
- This update does not yet connect each Staff portal module to the full corresponding data-entry screens or enforce View/Add/Edit/Delete permissions inside every existing module operation. That requires further app-wide permission wiring.
- PDF share/save chooser has not been tested on a physical Android device in this environment.
- No APK build was run here because Flutter/Dart SDK is not installed in this environment.
